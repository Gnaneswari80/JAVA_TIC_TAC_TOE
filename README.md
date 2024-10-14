# JAVA_TIC_TAC_TOE

import java.awt.*;
import java.text.NumberFormat;

import javax.swing.*;
import java.util.*;
public class GAME {

	static int player=2;
	static String sign;
	static JLabel winner_Label=new JLabel("");
	static String whoplay;
	static int winner=0;
	static int tiecount=0; 
	
	static JButton playAgain=new JButton("RePlay");
	static JButton quit=new JButton("Quit");
	 //int check[][]=new int[5][6];
	 static String str[][]=new String [3][3];
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		GAME ad=new GAME();
		
		JFrame f1=new JFrame("TIC TAC TOE");
		f1.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE );
		f1.setSize(1000,1000);
		
		JPanel p=new JPanel();
		p.setBorder(BorderFactory.createLineBorder(new Color(29,87,69), 230));
		p.setLayout(null);
		p.setBackground(new Color(40,43,115));
		f1.getContentPane().add(p);
		
		JLabel developer=new JLabel("Developed By Gnaneswari");
		developer.setBounds(650,0,400,100);
		developer.setFont(new Font("Arial",Font.BOLD,25));
		developer.setForeground(Color.orange);
		developer.setVisible(true);
		p.add(developer);
		
		JTextField tf=new JTextField(10);
		p.add(tf);tf.setVisible(false);
		tf.setText("2");
		
		
		JLabel head=new JLabel("TIC TAC TOE GAME");
		head.setBounds(300,100,400,100);
		head.setFont(new Font("Arial",Font.BOLD,40));
		head.setForeground(Color.RED);
		head.setVisible(true);
		p.add(head);
		
		
		//shows who want to play	
			JLabel whoplaying=new JLabel("Player X");
			whoplaying.setBounds(450, 520, 200, 100);
			p.add(whoplaying);
			whoplaying.setFont(new Font("Arial",Font.BOLD,25));
			whoplaying.setForeground(Color.MAGENTA);
			whoplaying.setVisible(true);


		///play again Button
		p.add(playAgain);
		playAgain.setBounds(650, 550,100,50);
		playAgain.setFont(new Font("Arial",Font.BOLD,20));
		playAgain.setForeground(Color.RED);
		playAgain.setVisible(true);
		
		///Quit BUTTON
		p.add(quit);
		quit.setBounds(230, 550,100,50);
		quit.setFont(new Font("Arial",Font.BOLD,20));
		quit.setForeground(Color.RED);
		quit.setVisible(true);
		
		//shows WHen The player is WINNER  AND TIE
		winner_Label.setBounds(350, 570, 200, 100);
		winner_Label.setFont(new Font("Arial",Font.BOLD,24));
		winner_Label.setForeground(Color.blue);
		p.add(winner_Label);
		
		

		JButton b1=new JButton("");;
		JButton b2=new JButton("");		
		JButton b3=new JButton("");
		JButton b4=new JButton("");
		JButton b5=new JButton("");
		JButton b6=new JButton("");
		JButton b7=new JButton("");
		JButton b8=new JButton("");
		JButton b9=new JButton("");
		
	    b1.setBounds(350, 250, 60, 60);
		p.add(b1);
		b1.setFont(new Font("Arial",Font.BOLD,30));
		b1.setForeground(Color.BLACK);
		b1.setBackground(new Color(214,171,203));
		b1.setBorder(BorderFactory.createLineBorder(Color.black,1));
	
		b2.setBounds(450, 250, 60, 60);
		p.add(b2);
		b2.setFont(new Font("Arial",Font.BOLD,30));
		b2.setForeground(Color.BLACK);
		b2.setBackground(new Color(214,171,203));
		b2.setBorder(BorderFactory.createLineBorder(Color.black,1));
		
		b3.setBounds(550, 250, 60, 60);
		p.add(b3);
		b3.setFont(new Font("Arial",Font.BOLD,30));
		b3.setForeground(Color.BLACK);
		b3.setBackground(new Color(214,171,203));
		b3.setBorder(BorderFactory.createLineBorder(Color.black,1));
		//2nd row
		b4.setBounds(350, 350, 60, 60);
		p.add(b4);
		b4.setFont(new Font("Arial",Font.BOLD,30));
		b4.setForeground(Color.BLACK);
		b4.setBackground(new Color(214,171,203));
		b4.setBorder(BorderFactory.createLineBorder(Color.black,1));
		
		b5.setBounds(450, 350, 60, 60);
		b5.setFont(new Font("Arial",Font.BOLD,30));
		b5.setForeground(Color.BLACK);
		p.add(b5);
		b5.setBackground(new Color(214,171,203));
		b5.setBorder(BorderFactory.createLineBorder(Color.black,1));
		
		b6.setBounds(550, 350, 60, 60);
		b6.setFont(new Font("Arial",Font.BOLD,30));
		b6.setForeground(Color.BLACK);
		p.add(b6);
		b6.setBackground(new Color(214,171,203));
		b6.setBorder(BorderFactory.createLineBorder(Color.black,1));
		//3rd row
		
	
		b7.setBounds(350, 450, 60, 60);
		b7.setFont(new Font("Arial",Font.BOLD,30));
		b7.setForeground(Color.BLACK);
		p.add(b7);
		b7.setBackground(new Color(214,171,203));
		b7.setBorder(BorderFactory.createLineBorder(Color.black,1));
		
		b8.setBounds(450, 450, 60, 60);
		b8.setFont(new Font("Arial",Font.BOLD,30));
		b8.setForeground(Color.BLACK);
		p.add(b8);
		b8.setBackground(new Color(214,171,203));
		b8.setBorder(BorderFactory.createLineBorder(Color.black,1));
		
		b9.setBounds(550, 450, 60, 60);
		p.add(b9);
		b9.setFont(new Font("Arial",Font.BOLD,30));
		b9.setForeground(Color.BLACK);
		b9.setBackground(new Color(214,171,203));
		b9.setBorder(BorderFactory.createLineBorder(Color.black,1));
		
		
		
		
		f1.setVisible(true); //Keep These Here ONLY ,,WE Get Perfect output
		
		

		
		
		
		//button 1 Click
		b1.addActionListener(e ->{
			try {
				//String s=tf.getText();
				String check=b1.getText();
				if(check!="X"&&check!="O"&&winner==0)
				{
				       player=Integer.parseInt(tf.getText());
				            if(player%2==0)
				            {
						       sign="X";
						       whoplaying.setText("PLAYER--O");}
					        else {
						         sign="O";
						         whoplaying.setText("PLAYER--X");}
					        player++;
					        tiecount++;
					tf.setText(Integer.toString(player));
					b1.setText(sign);
					str[0][0]=sign;
					
					//check
                     ad.check();
				
						
				}		
				
				
				
			}catch(NumberFormatException ex)
			{
				
			}
		});
///button2 click
		b2.addActionListener(e ->{
			try {
				//String s=tf.getText();
				//tf.setText(s+"1");
				String check=b2.getText();
				if(check!="X"&&check!="O"&&winner==0)
				{
				          player=Integer.parseInt(tf.getText());
				          if(player%2==0)
				            {
						       sign="X";
						       whoplaying.setText("PLAYER--O");}
					        else {
						         sign="O";
						         whoplaying.setText("PLAYER--X");}
				          tiecount++;
				      player++;
					tf.setText(Integer.toString(player));
				  b2.setText(sign);
				  str[0][1]=sign;
				  
				//check
				  ad.check();
						
				}	  
				
			}catch(NumberFormatException ex)
			{
				
			}
		});
		
		//button 3 Click
				b3.addActionListener(e ->{
					try {
						//String s=tf.getText();
						String check=b3.getText();
						if(check!="X"&&check!="O"&&winner==0)
						{
						       player=Integer.parseInt(tf.getText());
						       if(player%2==0)
					            {
							       sign="X";
							       whoplaying.setText("PLAYER--O");}
						        else {
							         sign="O";
							         whoplaying.setText("PLAYER--X");}
						       tiecount++;
							        player++;
							tf.setText(Integer.toString(player));
							b3.setText(sign);
							str[0][2]=sign;
							//check
							ad.check();
							
						}		
				
					
						
					}catch(NumberFormatException ex)
					{
						
					}
				});

				//button 4 Click
				b4.addActionListener(e ->{
					try {
						//String s=tf.getText();
						String check=b4.getText();
						if(check!="X"&&check!="O"&&winner==0)
						{
						       player=Integer.parseInt(tf.getText());
						       if(player%2==0)
					            {
							       sign="X";
							       whoplaying.setText("PLAYER--O");}
						        else {
							         sign="O";
							         whoplaying.setText("PLAYER--X");}						    
							        player++;
							        tiecount++;
							tf.setText(Integer.toString(player));
							b4.setText(sign);
							str[1][0]=sign;
							//check
							ad.check();
								}		
						
						
						
					}catch(NumberFormatException ex)
					{
						
					}
				});

				//button 5 Click
				b5.addActionListener(e ->{
					try {
						//String s=tf.getText();
						String check=b5.getText();
						if(check!="X"&&check!="O"&&winner==0)
						{
						       player=Integer.parseInt(tf.getText());
						       if(player%2==0)
					            {
							       sign="X";
							       whoplaying.setText("PLAYER--O");}
						        else {
							         sign="O";
							         whoplaying.setText("PLAYER--X");}
						        
							        player++;
							        tiecount++;
							tf.setText(Integer.toString(player));
							b5.setText(sign);
							str[1][1]=sign;
							
							//check
							ad.check();
					
						}		
					
						
						
					}catch(NumberFormatException ex)
					{
						
					}
				});


				//button 6 Click
				b6.addActionListener(e ->{
					try {
						//String s=tf.getText();
						String check=b6.getText();
						if(check!="X"&&check!="O"&&winner==0)
						{
						       player=Integer.parseInt(tf.getText());
						       if(player%2==0)
					            {
							       sign="X";
							       whoplaying.setText("PLAYER--O");}
						        else {
							         sign="O";
							         whoplaying.setText("PLAYER--X");}
						       
							        player++;
							        tiecount++;
							tf.setText(Integer.toString(player));
							b6.setText(sign);
							str[1][2]=sign;
							
							//check
							ad.check();
							}		
						//tfpl.setText(s+"1");
						
						
					}catch(NumberFormatException ex)
					{
						
					}
				});

				//button 7 Click
				b7.addActionListener(e ->{
					try {
						//String s=tf.getText();
						String check=b7.getText();
						if(check!="X"&&check!="O"&&winner==0)
						{
						       player=Integer.parseInt(tf.getText());
						       if(player%2==0)
					            {
							       sign="X";
							       whoplaying.setText("PLAYER--O");}
						        else {
							         sign="O";
							         whoplaying.setText("PLAYER--X");}
						        
							        player++;
							        tiecount++;
							tf.setText(Integer.toString(player));
							b7.setText(sign);
							str[2][0]=sign;
							
							//check
							ad.check();
						
						}		
						//tfpl.setText(s+"1");
					
						
					}catch(NumberFormatException ex)
					{
						
					}
				});

				//button 8 Click
				b8.addActionListener(e ->{
					try {
						//String s=tf.getText();
						String check=b8.getText();
						if(check!="X"&&check!="O"&&winner==0)
						{
						       player=Integer.parseInt(tf.getText());
						       if(player%2==0)
					            {
							       sign="X";
							       whoplaying.setText("PLAYER--O");}
						        else {
							         sign="O";
							         whoplaying.setText("PLAYER--X");}
						        
							        player++;
							        tiecount++;
							tf.setText(Integer.toString(player));
							b8.setText(sign);
							str[2][1]=sign;
							ad.check();
									
						}		
						//tfpl.setText(s+"1");
					
						
					}catch(NumberFormatException ex)
					{
						
					}
				});



				//button 1 Click
				b9.addActionListener(e ->{
					try {
						//String s=tf.getText();
						String check=b9.getText();
						if(check!="X"&&check!="O"&&winner==0)
						{
						       player=Integer.parseInt(tf.getText());
						       if(player%2==0)
					            {
							       sign="X";
							       whoplaying.setText("PLAYER--O");}
						        else {
							         sign="O";
							         whoplaying.setText("PLAYER--X");}
						       
							        player++;
							        tiecount++;
							tf.setText(Integer.toString(player));
							b9.setText(sign);
							str[2][2]=sign;
							
							ad.check();
							//check
							
						}		
			
						
						
					}catch(NumberFormatException ex)
					{
						
					}
				});

 
		playAgain.addActionListener(e ->{
			try {
				
				winner=0;
				b1.setText("");
				b2.setText("");
				b3.setText("");
				b4.setText("");
				b5.setText("");
				b6.setText("");
				b7.setText("");
				b8.setText("");
				b9.setText("");
				//sign="X";
				player=2;
				tiecount=0;
				tf.setText(Integer.toString(player));
				winner_Label.setText("");
				whoplay="PLAYER--X";
				whoplaying.setText(whoplay);
				for(int i=0;i<3;i++)
				{
					for(int j=0;j<3;j++)
					{
						str[i][j]="";		
					}
				}
				
				
			}catch(NumberFormatException ex){
				
			}
		});
		
		quit.addActionListener(e ->{
			try {
				f1.setVisible(false);
				
			}catch(NumberFormatException ex){
				
			}
		});
		
		
		
		
		}//main FUNCTION
	
	public void check()
	{
     if(tiecount==9)
	{
    	 winner_Label.setText("Game Tie");
	}
			
		
		if((str[0][0]==sign)&&(str[0][1]==sign)&&(str[0][2]==sign))
		{winner_Label.setText(sign+" Is The Winner");
		winner_Label.setVisible(true);
		winner=1;
		}
		
		else if((str[1][0]==sign)&&(str[1][1]==sign)&&(str[1][2]==sign))
		{
			winner_Label.setText(sign+" Is The Winner");winner=1;
		}
		else if((str[2][0]==sign)&&(str[2][1]==sign)&&(str[2][2]==sign))
		{
			winner=1;
			winner_Label.setText(sign+" Is The Winner");
		}
		else if((str[0][0]==sign)&&(str[1][0]==sign)&&(str[2][0]==sign))
		{winner_Label.setText(sign+" Is The Winner");winner=1;
			
		}
		else if((str[0][1]==sign)&&(str[1][1]==sign)&&(str[2][1]==sign))
		{winner_Label.setText(sign+" Is The Winner");
		winner=1;
		}
		else if((str[0][2]==sign)&&(str[1][2]==sign)&&(str[2][2]==sign))
		{winner_Label.setText(sign+" Is The Winner");
		winner=1;
		}
		else if((str[0][0]==sign)&&(str[1][1]==sign)&&(str[2][2]==sign))
		{winner_Label.setText(sign+" Is The Winner");winner=1;
			
		}
		else if((str[0][2]==sign)&&(str[1][1]==sign)&&(str[2][0]==sign))
		{winner_Label.setText(sign+" Is The Winner");
		winner=1;
		}
	

		
	}

}

