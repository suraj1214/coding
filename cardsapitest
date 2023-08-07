
package main;
        //Each card has a value and a suite.
    public class Card {
        int value;
        SUITE suite;

        public Card(int value, SUITE suite) {
            this.value = value;
            this.suite = suite;
        }

        public int getValue() {
            return value;
        }

        public SUITE getSuite() {
            return suite;
        }

        public void setValue(int value) {
            this.value = value;
        }

        public void setSuite(SUITE suite) {
            this.suite = suite;
        }

        @Override
        public String toString() {
            return "Card{" +
                    "value=" + value +
                    ", suite=" + suite +
                    '}';
        }
    }

package main;    
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.Random;

public class Deck {
    List<Card> cardDeck;

    public Deck() {
        this.cardDeck = new ArrayList<Card>();
        for(int value = 1 ; value <= 13 ; value++){
            for(SUITE suite : SUITE.values()){
             cardDeck.add(new Card(value,suite));
            }
        }
    }

    @Override
    public String toString() {
        return "Deck{" +
                "cardDeck=" + cardDeck +
                '}';
    }

    public void shuffle(){
        Random rand = new Random();
        //Generate two random numbers between 0 to 51
        for(int i = 0 ; i < 20 ; i ++){
            int firstCard = rand.nextInt(52);
            int secondCard = rand.nextInt(52);
            Collections.swap(cardDeck,firstCard,secondCard);
        }
    }

    public void dealCard(Player player){
       //Get next card and add to hand of the player
        Card removedCard = cardDeck.remove(0);
        player.getHand().add(removedCard);
    }

    public Card dealCard(){
        Card removedCard = cardDeck.remove(0);
        return removedCard;
    }

    //Size of the deck for testing purpose
    public int getSizeOfDeck(){
        return cardDeck.size();
    }
}


package main;    
import java.util.ArrayList;
import java.util.List;

public class Player {
    List<Card> hand;

    public Player() {
        this.hand = new ArrayList<Card>();
    }

    public List<Card> getHand() {
        return hand;
    }

    @Override
    public String toString() {
        return "Player{" +
                "hand=" + hand +
                '}';
    }
}



package main;

public enum SUITE {
    HEART,
    SPADE,
    CLUB,
    DIAMOND
}

 
@Test  
public class DeckOfCardsAPITest{
        Deck deck = new Deck();
        System.out.println(deck);
        System.out.println("Size of deck is: "+deck.getSizeOfDeck());
        deck.shuffle();
        System.out.println("shuffling is "+deck);

        Player player1 = new Player();
        Player player2 = new Player();

        deck.dealCard(player1);
        System.out.println("Size of deck "+deck.getSizeOfDeck());
        deck.dealCard(player2);
        System.out.println("Size of deck "+deck.getSizeOfDeck());

        System.out.println("Hand of player 1 is "+player1.getHand());
        System.out.println("Hand of player 2 is "+player2.getHand());

        player1.getHand().add(deck.dealCard());
    }
}
