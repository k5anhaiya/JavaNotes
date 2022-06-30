import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.time.OffsetTime;
import java.util.*;

public class exam_Timer 
{
	JFrame fr=new JFrame("Stop Watch");
	JLabel la=new JLabel("00:00");
	int m=0,s=0;
	int noq=1;
	public exam_Timer()
	{
		fr.setSize(400,400);
		fr.setResizable(false);
		fr.setLocationRelativeTo(null);
		fr.setDefaultCloseOperation(3);
		fr.setLayout(new FlowLayout(FlowLayout.CENTER,180,150));
		fr.add(la);
		setTime();
		new timeThread().start();
		la.setFont(new Font("lucida calligraphy",Font.BOLD,20));
		fr.setVisible(true);
	}
	private void setTime() 
	{
		m=noq/2;
		if(noq%2!=0)
			s=30;
	}
	class timeThread extends Thread
	{
		public void run()
		{
			while(true)
			{
				String time=(m<10?"0"+m:m)+":"+(s<10?"0"+s:s);
				la.setText(time);
				
				try 
				{
					Thread.sleep(1000);
				} catch (Exception ex) {}
				if(s==0)
				{
					if(m==0)
						break;
					s=60;
					m--;
				}
				s--;
				
			}
		}
	}
	public static void main(String[] args) 
	{
		new exam_Timer();
	}

}
