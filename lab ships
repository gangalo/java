import java.util.ArrayList;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

public class Main {
    public static void main(String[] args) {
        Ship[] ships = new Ship[3];
        ExecutorService exSer = Executors.newFixedThreadPool(2);
        ArrayList<Future>result = new ArrayList<>();
        for (Ship ship : ships){
            result.add(exSer.submit(new Ship(10)));
        }
        exSer.shutdown();
    }
}

class Ship implements Runnable {
    private int box;

    public Ship(int box) {
        this.box = box;
    }
    

    public int getBox() {
        return box;
    }

    public void setBox(int box) {
        this.box = box;
    }

    @Override
    public void run() {
        for (int i = this.box; i > 0; i -= 1) {
            this.box -= 1;

            try{
                Thread.sleep(500);
            }catch (InterruptedException e){
                System.out.println(e);
            }
        }
        System.out.println("The ship is empty. Box - " + this.box);
    }
}
