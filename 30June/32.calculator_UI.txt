import javax.swing.*;
import java.awt.*;

public class calculator 
{
	JFrame fr=new JFrame("Calculator");
	JTextField tb=new JTextField();
	JButton [] bt=new JButton[20];
	
	public calculator()
	{
		fr.setSize(400,400);
		fr.setLocationRelativeTo(null);
		fr.setResizable(false);
		fr.setLayout(null);
		fr.setDefaultCloseOperation(3);
		addTextField();
		fr.setVisible(true);
	}
	private void addTextField()
	{
		tb.setBounds(20,20,350,30);
		fr.add(tb);
		tb.setFont(new Font("Verdana",1,15));
		tb.setEditable(false);
		tb.setBackground(Color.white);
		tb.setBorder(BorderFactory.createLineBorder(Color.red,2));  //color.red,thickness of borderline.
		addButtons();
	}
	private void addButtons()
	{
		JPanel pa=new JPanel();
		pa.setBounds(20,90,350,250);
		//pa.setBackground(Color.yellow);
		fr.add(pa);
		pa.setLayout(new GridLayout(5,4,5,5));  //GridLayout(row,column,horizontalgap,verticalgap)
		String []str= {"BACK","CE","C","%","7","8","9","/","4","5","6","*","1","2","3","-","0",".","=","+"};
		Font fo=new Font("verdana",1,15);
		for(int i=0;i<20;i++)
		{
			bt[i]=new JButton(str[i]);
			bt[i].setFont(fo);
			pa.add(bt[i]);
			if(i==3||i==7||i==11||i==15||i==19||i==18)
			{
				bt[i].setForeground(Color.red);
			}
		}
		bt[3].setFont(new Font("elephant",0,25));
		bt[7].setFont(new Font("elephant",0,25));
		bt[11].setFont(new Font("elephant",0,25));
		bt[15].setFont(new Font("elephant",0,25));
		bt[19].setFont(new Font("elephant",0,25));
		bt[18].setFont(new Font("elephant",0,25));
	}
	public static void main(String[] args) 
	{
		new calculator();
	}
}

