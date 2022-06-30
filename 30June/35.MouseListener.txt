import java.awt.*;
import java.awt.event.*;
import javax.swing.*;


public class App 
{
	JFrame frame=new JFrame("Mouse");
	JPanel panel=new JPanel();
	JLabel la=new JLabel("India is great country.");
	public App()
	{
		frame.setSize(500,400);
		frame.setDefaultCloseOperation(3);
		frame.setResizable(false);
		frame.setLocationRelativeTo(null);
		frame.add(panel);
		panel.add(la);
		la.setFont(new Font("Lucida Calligraphy",0,25));
		la.addMouseListener(new TextListener());
		frame.setVisible(true);
	}
	class TextListener implements MouseListener
	{
		String old;
		public void mouseClicked(MouseEvent evt) {}
		public void mousePressed(MouseEvent evt) {}
		public void mouseReleased(MouseEvent evt) {}
		public void mouseEntered(MouseEvent evt)
		{
			old=la.getText();
			la.setText("Bharat is Mahan");
			la.setForeground(Color.red);
		}
		public void mouseExited(MouseEvent evt) 
		{
			la.setText(old);
			la.setForeground(Color.black);
		}	
	}

	public static void main(String[] args) 
	{
		new App();
	}

}
