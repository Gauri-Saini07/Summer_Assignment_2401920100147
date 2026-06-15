1) OOPS PROBLEM
package oops2.string;

import oops2.Playable;

public class veena implements Playable {
    @Override
    public void play() {
        System.out.println("Playing veena");
    }
} 

package oops2.wind;

import oops2.Playable;

public class Saxophone implements Playable {
    @Override
    public void play() {
        System.out.println("Playing Saxophone");
    }
}

package oops2;

public interface Playable {
    void play();
}

package live;

import oops2.Playable;
import oops2.string.veena;
import oops2.wind.Saxophone;

public class Test {
    public static void main(String[] args) {
        veena v = new veena();
        v.play();
        Saxophone s = new Saxophone();
        s.play();
        Playable p;
        p = new veena();
        p.play();
        p = new Saxophone();
        p.play();
    }
}  

OUTPUT:
Playing veena
Playing Saxophone
Playing veena
Playing Saxophone


