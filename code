import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class Calculator implements ActionListener  {

	JFrame frame;
	JTextField textField;
	JButton numButton[] = new JButton[10];
	JButton funButton[] = new JButton[9];
	JButton addButton, subButton, mulButton, divButton;
	JButton decButton, equalButton, delButton, clrButton;
	JPanel Panel;
	ImageIcon icon;
	Font myFont = new Font("MV BOLI", Font.BOLD,30);
	
	double num1 = 0, num2 = 0, result = 0;
	char operator;
	
	Calculator(){
		icon = new ImageIcon("icon.png");
		//frame.setIconImage(icon.getImage());
		frame = new JFrame("Calculator");
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(400, 520);
		frame.setLayout(null);
		
		textField = new JTextField();
		textField.setBounds(30,25,320,50);
		textField.setBackground(Color.cyan);
		textField.setFont(new Font("Helvetica", Font.BOLD,30));
		textField.setEditable(false);
		
		addButton =new JButton("+");
		subButton =new JButton("-");
		mulButton =new JButton("*");
		divButton =new JButton("/");
		decButton =new JButton(".");
		equalButton =new JButton("=");
		delButton =new JButton("Delete");
		clrButton =new JButton("CE");
		//addButton =new JButton("+");
		
		funButton[0] = addButton;
		funButton[1] = subButton ;
		funButton[2] = mulButton;
		funButton[3] = divButton;
		funButton[4] = decButton;
		funButton[5] = equalButton;
		funButton[6] = delButton;
		funButton[7] = clrButton;
		
		for(int i=0; i < 8; i++) {
			funButton[i].addActionListener(this);
			funButton[i].setFont(myFont);
			funButton[i].setFocusable(false);
		}
		
		for(int i = 0; i< 10; i++) { 
			numButton[i] = new JButton(String.valueOf(i));
			numButton[i].addActionListener(this);
			numButton[i].setFont(myFont);
			numButton[i].setFocusable(false);
		}
		
		delButton.setBounds(30,420,145,50);
		clrButton.setBounds(205,420,145,50);
		
		
		Panel = new JPanel();
		Panel.setBounds(30,100, 320,310);
		//Panel.setBackground(Color.gray);
		Panel.setLayout(new GridLayout(5,5,10,10));

		Panel.add(numButton[7]);
		Panel.add(numButton[8]);
		Panel.add(numButton[9]);
		Panel.add(divButton);
		Panel.add(numButton[4]);
		Panel.add(numButton[5]);
		Panel.add(numButton[6]);
		Panel.add(mulButton);
		Panel.add(numButton[1]);
		Panel.add(numButton[2]);
		Panel.add(numButton[3]);
		Panel.add(subButton);
		Panel.add(decButton);
		Panel.add(numButton[0]);
		Panel.add(equalButton);
		Panel.add(addButton);
		
		
		
		frame.add(Panel);
		frame.add(delButton);
		frame.add(clrButton);
		frame.add(textField);		
		frame.setVisible(true);
		
	}
	
	
	public static void main(String[] args) {
		
		new Calculator();
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		for(int i = 0; i < 10; i++) {
			if(e.getSource() == numButton[i]) {
				textField.setText(textField.getText().concat(String.valueOf(i)));
			}
		}
		if(e.getSource() == decButton) {
			textField.setText(textField.getText().concat("."));
		}
		if(e.getSource() == addButton) {
			num1 = Double.parseDouble(textField.getText());
			operator = '+';
			textField.setText("");
			
		}
		if(e.getSource() == subButton) {
			if(textField.getText().equals("")) {
				Double temp= Double.parseDouble(textField.getText());
				temp*= -1;
				textField.setText(String.valueOf(temp));
			}
			else {
				num1 = Double.parseDouble(textField.getText());
				operator = '-';
				textField.setText("");
			}
		}
		if(e.getSource() == mulButton) {
			num1 = Double.parseDouble(textField.getText());
			operator = '*';
			textField.setText("");
			
		}
		if(e.getSource() == divButton) {
			num1 = Double.parseDouble(textField.getText());
			operator = '/';
			textField.setText("");
			
		}
		if(e.getSource() ==  equalButton) {
			num2 = Double.parseDouble(textField.getText());
			switch(operator){
			case'+':
				result = num1 + num2;
				break;
			case'-' :
				result = num1 - num2;
				break;
			case'/' :
				result = num1 / num2;
				break;
			case'*' :
				result = num1 * num2;
				break;
			}
			textField.setText(String.valueOf(result));
			num1 = result;
		}
		if(e.getSource() == clrButton) {
			textField.setText("");
		}
		if(e.getSource() == delButton) {
			String  str = textField.getText();
			textField.setText("");
			for(int i = 0; i < str.length() - 1; i++) {
				textField.setText(textField.getText()+ str.charAt(i));
			}
		}
	}

}
