# Digital-clock
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Swing extends JFrame {
    
    public JLabel heading;
    public JLabel clockLabel;
    public Font font = new Font("Arial", Font.BOLD, 50);
    
    public Swing() {
        super("Digital Clock"); 
        setSize(400, 400);
        setLocation(300, 50);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        createGUI();
        setVisible(true);
    }
    
    public void createGUI() {
        heading = new JLabel("Digital Clock");
        clockLabel = new JLabel("Clock");
        heading.setFont(font);

        this.setLayout(new BorderLayout());
        this.add(heading, BorderLayout.NORTH);
        this.add(clockLabel, BorderLayout.CENTER);
    }

    public void startclock() {
        Timer timer = new Timer(1000, new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String dateTime = new Date().toString();   //using simple conversion of date and time into string to display
              /*   Date d=new Date();                     //using SimpleDateFormat class to format date to display
                SimpleDateFormat sdf= new SimpleDateFormat("hh:mm:ss:a");
                String dateTime=sdf.format(d);*/
                clockLabel.setText(dateTime);
            }
        });
        timer.start();  
    }
    
    public static void main(String[] args) {
        Swing s = new Swing();
        s.startclock();
    }
}
