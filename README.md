# Java

package component;

import javax.microedition.midlet.*;

import com.sun.lwuit.*;

import com.sun.lwuit.events.*;

import com.sun.lwuit.table.TableLayout;

import java.io.IOException;
 
public class Apple2 extends MIDlet implements ActionListener
{
  	
	Form mainForm;
 
  	String [] content = {"$1099", "$1299", "$799", "$399", "$699"};
  	ComboBox combobox;
 
  	Label othercostlabel;
 
  	TextField firstfield, secondfield, thirdfield, fourthfield, fifthfield;
  	Label firstlabel, secondlabel, thirdlabel, fourthlabel, fifthlabel;
 
  	Button firstbutton, secondbutton, thirdbutton, fourthbutton, fifthbutton, cmdcompute;
  	
    private Image firstImage;
    private Image secondImage;
    private Image thirdImage;
    private Image fourthImage;
    private Image fifthImage;
 
  	public void startApp()
	{
          Display.init(this);
      	mainForm= new Form ("Apple Store");
      	Command exitCommand = new Command ("Exit");
          mainForm.addCommand(exitCommand);
 
      	TableLayout layout = new TableLayout(3,5);
          mainForm.setLayout(layout);
          TableLayout.Constraint constraint = layout.createConstraint();
 
	      constraint.setWidthPercentage(50);
 
	      try {
                 firstImage = Image.createImage("/Imac.png");
                 secondImage = Image.createImage("/IpadAir.png");
                 thirdImage = Image.createImage("/Iphone6.png");
                 fourthImage = Image.createImage("/Iwatch.png");
                 fifthImage = Image.createImage("/MacbookPro.png");
 
       	      firstbutton = new Button("", firstImage);
                 secondbutton = new Button("", secondImage);
                 thirdbutton = new Button("", thirdImage);
                 fourthbutton = new Button("", fourthImage);
   	          fifthbutton = new Button("",fifthImage);
       	}
           catch (IOException ex)
       	{
       	}
 
	      mainForm.addComponent(firstbutton);
          mainForm.addComponent(secondbutton);
          mainForm.addComponent(thirdbutton);
          mainForm.addComponent(fourthbutton);
          mainForm.addComponent(fifthbutton);
      	
	      firstlabel = new Label ("1099");
          mainForm.addComponent(firstlabel);
      	secondlabel = new Label ("199");
      	mainForm.addComponent(secondlabel);
           thirdlabel = new Label ("799");
          mainForm.addComponent(thirdlabel);
           fourthlabel = new Label ("399");
          mainForm.addComponent(fourthlabel);
           fifthlabel = new Label ("699");
          mainForm.addComponent(fifthlabel);
      	
	      firstfield = new TextField(3);
          firstfield.setConstraint(TextField.NUMERIC);
          mainForm.addComponent(firstfield);
      	secondfield = new TextField(3);
      	secondfield.setConstraint(TextField.NUMERIC);
          mainForm.addComponent(secondfield);
      	thirdfield = new TextField(3);
          thirdfield.setConstraint(TextField.NUMERIC);
          mainForm.addComponent(thirdfield);
      	fourthfield = new TextField(3);
          fourthfield.setConstraint(TextField.NUMERIC);
          mainForm.addComponent(fourthfield);
      	fifthfield = new TextField(3);
          fifthfield.setConstraint(TextField.NUMERIC);
          mainForm.addComponent(fifthfield);
         
	      cmdcompute = new Button ("Total");
          cmdcompute.setTextPosition(Component.BOTTOM);
          mainForm.addComponent(cmdcompute);
      	
	      cmdcompute.addActionListener(new ActionListener()
                  {
    	      public void actionPerformed(ActionEvent ae)
                {
        	      calculateJButtonActionPerformed(ae);
                }
                   
                  });
                 
      	      mainForm.show();
	}
  	
  	private void calculateJButtonActionPerformed(ActionEvent event)
	{
	      int firstquantity;
      	double tax= 0.088, firstprice,total;
      	
      	
	      firstprice = Double.parseDouble(firstlabel.getText());
      	firstquantity = Integer.parseInt(firstfield.getText());
      	
	      total = firstprice*firstquantity*tax+(firstprice*firstquantity);
     	
      	
	}
 
	      protected void pauseApp() {
    	throw new UnsupportedOperationException("Not supported yet.");
	}
 
	protected void destroyApp(boolean unconditional) throws MIDletStateChangeException {
    	throw new UnsupportedOperationException("Not supported yet.");
	}
 
	public void actionPerformed(ActionEvent ae) {
    	throw new UnsupportedOperationException("Not supported yet.");
	}
 
 

}



