# oibsip_taskno2
package com.company;
import java.util.Random;
import java.util.Scanner;

class Game{
    public int number;
    public int inputNumber;
    public int noOfGuesses=0;



    public int getNoOfGuesses() {
        return noOfGuesses;
    }

    public void setNoOfGuesses(int noOfGuesses) {
        this.noOfGuesses = noOfGuesses;
    }


     Game(){
        Random ran = new Random();
        this.number = ran.nextInt(100);


    }
    void takeUserInput(){
        System.out.println("Guess the number");
        Scanner sc = new Scanner(System.in);
        inputNumber = sc.nextInt();


    }
    boolean isCorrectNumber(){
        noOfGuesses++;
        if (inputNumber == number){

            System.out.format("Yes you guesses it right, it was %d\n You guessed it in %d attempts ", number, noOfGuesses);

        }
        else if (inputNumber<number){
            System.out.println("too low");
        }
        else if (inputNumber>number){
            System.out.println("too high");
        }
        return false;

    }
}
public class guessNo {
    public static void main(String[] args) {


        Game g = new Game();
        boolean b = false;
        while(!b) {
            g.takeUserInput();
            b = g.isCorrectNumber();
            System.out.println(b);
        }

    }
}
