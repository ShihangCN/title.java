# title.java
import java.awt.Graphics;
import java.awt.Image;
import java.awt.Rectangle;
 
import javax.swing.ImageIcon;
 
public class Tile {
 
    private Rectangle[] blocks; // Tiles - invisible
    private Image[] blockImage; // Image for the tile
    private Image RED_LAND; // Actual PNG image
    int arraySize = 500;
    int x, y;
 
    public Tile(){
         
        RED_LAND = new ImageIcon("C:/Users/Cathy/Desktop/land1s.png").getImage();
        blocks = new Rectangle[500];
        blockImage = new Image[500];
         
        loadArrays();
    }
 
    private void loadArrays() {
        for (int i = 0; i < arraySize; i++) {
 
            if (x >= 500) {
                x = 0;
                y += 20;
            }
 
            blockImage[i] = RED_LAND;
            blocks[i] = new Rectangle(x, y, 20, 20);
 
            x += 20;
        }
    }
 
    public void draw(Graphics g) {
        for (int i = 0; i < arraySize; i++) {
            g.drawImage(blockImage[i], blocks[i].x, blocks[i].y, null);
        }
 
    }
 
}
