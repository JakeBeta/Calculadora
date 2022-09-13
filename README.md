# Calculadora

### DS131 – Linguagem de Programação Orientada a Objetos I

### Prof. Dieval Guizelini

# Atividade Avaliativa: calculadora...
Desenvolva em Java utilizando a interface SWING uma calculadora para as quatro operações aritméticas em 
que as entradas são realizadas apenas pelos botões e o display é apresentado por JTextField não editável. 
Os botões (de ações do usuário) são um para cada digito numérico (0 a 9), um para cada operador aritmético 
(+ - / e *), um para a operação de limpar (C) e um para o sinal de =. 
O programa deverá evitar erros de entrada, como iniciar as operações com multiplicação ou divisão e tratar a 
ambiguidade dos sinais + e – para diferenciar operador do sinal que identifica números positivos e negativos. 
Considere na solução os estados indicado abaixo e as modificações de estados decorrido das ações dos 
usuários. Para isso, utilize um enum (como demonstrado abaixo) para representar e manter os estados.
```java
enum EstadoCalculadora {
  INICIAL, IGNORADO, ENTRADA1, OPERADOR, ENTRADA2, CALCULANDO
};
private EstadoCalculadora estadoCalc = EstadoCalculadora.INICIAL;
```

# Diagrama de estado
![image](https://user-images.githubusercontent.com/64230498/189785518-95018c58-3877-4606-b4dd-620e31e09413.png)


# Interface gráfica

Para a interface, crie um JForm, defina o layout 
BorderLayout e coloque dois JPanel, um na região NORTH e 
outro na região CENTER. No primeiro JPanel será colocado o 
“display” e no segundo os botões. No 1º JPanel o layout 
pode ser o Free, porém ancore o TextField nas quatro 
bordas do JPanel. No segundo JPanel, defina o Layout 
GridLayout para 4 linhas e 4 colunas e o espaçamento entre 
os objetos com tamanho 2. O resultado esperado é 
apresentado na figura.

Todas as ações do usuário terão que ser “detectadas” e 
tratadas na própria classe do Form, use para isso o 
ActionListener como apresentado em sala. NÃO CRIE UM 
LISTERNER PARA CADA BOTÃO. E não esqueça de colocar no 
método construtor as chamadas para os botões “avisarem” 
o form da ação do usuário. Exemplo:
```java
initComponents(); 
button0.addActionListener(this); 
button1.addActionListener(this); 
```
![image](https://user-images.githubusercontent.com/64230498/189785280-3a4fb157-e946-40dc-93a2-8e9b58fd2b83.png)


Recomendo iniciar o exercício com o modelo abaixo.
Importante: não crie um listener para cada botão.

```java
public class CalculadoraFrame extends javax.swing.JFrame implements ActionListener {
  enum EstadoCalculadora {
  INICIAL, IGNORADO, ENTRADA1, OPERADOR, ENTRADA2, CALCULANDO
};
private EstadoCalculadora estadoCalc = EstadoCalculadora.INICIAL;
private int num1 = 0, num2 = 0;
privete char sinal = '+';
}
```

IDE: INTELLIJ Aluno: Thiago dos Santos GRR20211601
