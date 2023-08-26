

<img width="287" alt="Basic_Calculator image" src="https://github.com/MahfuzulIslamPranto/Java_Basic_Calculator_using_AWT/assets/121658967/9576b9a0-0cb9-4f5c-a4ad-33b981d4ec7f">

    package basiccalculator;
    import java.awt.*;
    import java.awt.event.*;
    public class BasicCalculator extends WindowAdapter implements ActionListener{
        Frame frame;
        Button button,bt1,bt2,bt3,bt4,bt5,bt6,bt7,bt8,bt9,bt0,btac,btmod,btback,btequal,btmul,btdiv,btadd,btsub,btneg,btpt;
        Label label;
        double n1,n2,check,result;
    BasicCalculator(){
        frame = new Frame("Basic Calculator");
        frame.setBackground(Color.cyan);
        button = new Button();
        label= new Label();
        label.setFont(new Font("SansSerif",Font.BOLD, 40));
        label.setForeground(Color.DARK_GRAY);
        
        label.setBounds(50,50,300,90);
        label.setBackground(Color.WHITE);
        
        //button_utilities:
        
        //1st row
        btac=new Button("AC");
        btac.setBounds(50,160,60,60);
        btac.setForeground(Color.red);
        btac.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btac);
        btmod=new Button("%");
        btmod.setBounds(130,160,60,60);
        btmod.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btmod);
        btneg=new Button("+/-");
        btneg.setBounds(210,160,60,60);
        btneg.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btneg);
        btback=new Button("Back");
        btback.setBounds(290,160,60,60);
        btback.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btback);
        
        //2nd row
        bt1=new Button("1");
        bt1.setBounds(50,230,60,60);
        bt1.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt1);
        bt2=new Button("2");
        bt2.setBounds(130,230,60,60);
        bt2.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt2);
        bt3=new Button("3");
        bt3.setBounds(210,230,60,60);
        bt3.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt3);
        btadd=new Button("+");
        btadd.setBounds(290,230,60,60);
        btadd.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btadd);
        
        //3rd row
        bt4=new Button("4");
        bt4.setBounds(50,300,60,60);
        bt4.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt4);
        bt5=new Button("5");
        bt5.setBounds(130,300,60,60);
        bt5.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt5);
        bt6=new Button("6");
        bt6.setBounds(210,300,60,60);
        bt6.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt6);
        btsub=new Button("-");
        btsub.setBounds(290,300,60,60);
        btsub.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btsub);
        
        //4th row
        bt7=new Button("7");
        bt7.setBounds(50,370,60,60);
        bt7.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt7);
        bt8=new Button("8");
        bt8.setBounds(130,370,60,60);
        bt8.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt8);
        bt9=new Button("9");
        bt9.setBounds(210,370,60,60);
        bt9.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt9);
        btmul=new Button("*");
        btmul.setBounds(290,370,60,60);
        btmul.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btmul);
        
        //5th row
        btpt=new Button(".");
        btpt.setBounds(50,440,60,60);
        btpt.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btpt);
        bt0=new Button("0");
        bt0.setBounds(130,440,60,60);
        bt0.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(bt0);
        btequal=new Button("=");
        btequal.setBounds(210,440,60,60);
        btequal.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btequal);
        btdiv=new Button("/");
        btdiv.setBounds(290,440,60,60);
        btdiv.setFont(new Font("SansSerif",Font.BOLD, 20));
        frame.add(btdiv);
        
        bt1.addActionListener(this);
        bt2.addActionListener(this);
        bt3.addActionListener(this);
        bt4.addActionListener(this);
        bt5.addActionListener(this);
        bt6.addActionListener(this);
        bt7.addActionListener(this);
        bt8.addActionListener(this);
        bt9.addActionListener(this);
        bt0.addActionListener(this);
        btpt.addActionListener(this);
        btmul.addActionListener(this);
        btdiv.addActionListener(this);
        btadd.addActionListener(this);
        btsub.addActionListener(this);
        btmod.addActionListener(this);
        btback.addActionListener(this);
        btneg.addActionListener(this);
        btequal.addActionListener(this);
        btac.addActionListener(this);

        frame.addWindowListener(this);
        
        frame.add(label);
        frame.setLayout(null);
        frame.add(button);
        frame.add(label);
        frame.setSize(400,530);
        frame.setVisible(true);   
    }
    
    @Override
    public void windowClosing(WindowEvent e) {
        frame.dispose();
    }
    @Override
    public void actionPerformed(ActionEvent e) {
        String lt,ltf = null;
        if(e.getSource()==bt1){
            lt=label.getText();
            ltf=lt+"1";
            label.setText(ltf);
        }
        if(e.getSource()==bt2){
            lt=label.getText();
            ltf=lt+"2";
            label.setText(ltf);
        }
        if(e.getSource()==bt3){
            ltf=label.getText()+"3";
            label.setText(ltf);
        }
        if(e.getSource()==bt4){
            lt=label.getText();
            ltf=lt+"4";
            label.setText(ltf);
        }
        if(e.getSource()==bt5){
            lt = label.getText();
            ltf=lt+"5";
            label.setText(ltf);
        }
        if(e.getSource()==bt6){
            lt = label.getText();
            ltf=lt+"6";
            label.setText(ltf);
        }
        if(e.getSource()==bt7){
            lt = label.getText();
            ltf=lt+"7";
            label.setText(ltf);
        }
        if(e.getSource()==bt8){
            lt = label.getText();
            ltf=lt+"8";
            label.setText(ltf);
        }
        if(e.getSource()==bt9){
            lt = label.getText();
            ltf=lt+"9";
            label.setText(ltf);
        }
        if(e.getSource()==bt0){
            lt = label.getText();
            ltf=lt+"0";
            label.setText(ltf);
        }
        if(e.getSource()==btneg){
            lt=label.getText();
            ltf="-"+lt;
            label.setText(ltf);
        }
        if(e.getSource()==btpt){
            lt = label.getText();
            ltf=lt+".";
            label.setText(ltf);
        }
        if(e.getSource()==btmul){
            try{
                n1 = Double.parseDouble(label.getText());
            }catch(NumberFormatException frame){
                label.setText("Invalid format");
            }
            ltf="";
            label.setText(ltf);
            check=1;
        }
        if(e.getSource()==btdiv){
            try{
                n1 = Double.parseDouble(label.getText());
            }catch(NumberFormatException frame){
                label.setText("Invalid format");
            }
            ltf="";
            label.setText(ltf);
            check=2;
        }
        if(e.getSource()==btadd){
            try{
                n1 = Double.parseDouble(label.getText());
            }catch(NumberFormatException frame){
                label.setText("Invalid format");
            }
            ltf="";
            label.setText(ltf);
            check=3;
        }
        if(e.getSource()==btsub){
            try{
                n1=Double.parseDouble(label.getText());
            }catch(NumberFormatException frame){
                label.setText("Invalid format");
            }
            ltf="";
            label.setText(ltf);
            check=4;
        }
        if(e.getSource()==btmod){
            try{
                n1=Double.parseDouble(label.getText());
            }catch(NumberFormatException frame){
                label.setText("Invalid format");
            }
            ltf="";
            label.setText(ltf);
            check=5;
        }
        if(e.getSource()==btback){
            lt=label.getText();
            try{
                ltf=lt.substring(0, lt.length()-1);
            }catch(StringIndexOutOfBoundsException frame){
                
            }
            label.setText(ltf);
        }
        if(e.getSource()==btequal){
            try{
                n2=Double.parseDouble(label.getText());
            }catch(Exception frame){
                label.setText("Enter number first");
            }
            if(check==1){
                result=n1*n2;
            }
            if(check==2){
                result=n1/n2;
            }
            if(check==3){
                result=n1+n2;
            }
            if(check==4){
                result=n1-n2;
            }
            if(check==5){
                result=n1%n2;
            }
            label.setText(String.valueOf(result));
        }
        if(e.getSource()==btac){
            n1=0;
            n2=0;
            result=0;
            check=0;
            ltf="";
            label.setText(ltf);
            
        }
    }
    
    
    public static void main(String[] args) {
        new BasicCalculator();
    }
}
