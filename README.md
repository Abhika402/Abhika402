package com.comapny.ATM_Machine;


import java.util.Scanner;


class A{
    int PIN=1234;
    float Balance;



  public void checkpin(){
      System.out.println("Enter the Pin:");
      Scanner sc=new Scanner (System.in);
      int enterpin=sc.nextInt();
      if(enterpin==PIN){
          menu();

      }
      else {
          System.out.println("Please enter valid pin:");
checkpin();
      }

    }
    public void menu(){
        System.out.println("ENTER YOUR CHOICE:");
        System.out.println("1.CHECK AC BALANCE:");
        System.out.println("2.WITHDRAW MONEY");
        System.out.println("3.DEPOSIT MONEY");
        System.out.println("4.EXIT");
        Scanner sc=new Scanner(System.in);
        int opt=sc.nextInt();

        if (opt==1){
            checkbalance();
        }
        else if(opt==2){
            withdrawmoney();

        }
        else if (opt==3){
            depositmoney();

        }
        else if(opt==4){
            return;
        }
        else{
            System.out.println("Please enter valid choice:");

        }

    }

    public void checkbalance(){

        System.out.println("BALANCE:"+Balance);
        menu();
    }

    public void withdrawmoney(){
        System.out.println("ENTER AMOUNT TO WITHDRAW:");
        Scanner sc=new Scanner (System.in);
        float amount=sc.nextFloat();

        if(amount>Balance){
            System.out.println("Insufficient Balance:");
        }
        else{
            Balance=amount-Balance;
            System.out.println(" Amount Withdraw Successfully:");
            menu();
        }
    }

    public void depositmoney(){

        System.out.println("ENTER AMOUNT TO  DEPOSIT:");
        Scanner sc=new Scanner(System.in);
        float amount=sc.nextFloat();
        Balance=amount+Balance;
        menu();
    }
}

public class Main {
    public static void main(String[] args) {

        A obj=new A();
        obj.checkpin();

    }
}
