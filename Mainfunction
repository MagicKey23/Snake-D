using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace WindowsFormsApplication1
{
    public partial class formMain : Form
    {
        private int direction = 0; // The direction
        private int score = 1; // the score
        private Timer gameLoop = new Timer(); // The timer
        private Random rand = new Random(); // The random
        private Graphics graphics;// the graphics
        private Food food; // The Food object that i made
        private Snake snake; // The snake ojecct that i made 

        public formMain()
        {
            InitializeComponent(); // Call the component from Design
            snake = new Snake(); // Call the object Snake, component
            food = new Food(rand); // call the object food, component
            gameLoop.Interval = 75;// Set the timer 
            gameLoop.Tick += Update;// Run the frame per second


        }



        private void formMain_KeyDown(object sender, KeyEventArgs e)
        {

            switch (e.KeyData) // e.KeyData, e will access to KeyData where it store information about the key.
            {
                case Keys.Enter: // Send the information to keydata that player hit enter
                    if (lblMenu.Visible) // Check the condition if the player have the menu on 
                    
                        lblMenu.Visible = false;  // it is on it turn invisible
                        gameLoop.Start(); // The timer start, start the game
                    break;

                case Keys.Space: // Send the information to keydata that player hit space, this use to pause the game

                    if (!lblMenu.Visible) // Check the condition invisible
                    
                        gameLoop.Enabled = (gameLoop.Enabled) ? false : true;// if it indeed invisible, the time stop
                    
                    
                    break;
                case Keys.Down: // If the player hit key down
                    if (direction != 3)// the player can't go up
                        direction = 1; // the player going down

                    break;
                case Keys.Up:
                    if (direction != 1)// the player can't go down
                        direction = 3; // The player go up

                    break;
                case Keys.Left:
                    if (direction != 0) // The player can't go right
                        direction = 2; // the player go left

                    break;
                case Keys.Right:

                    if (direction != 2) // the player go left
                        direction = 0;// the player go right
                    break;
            }
        }

        private void formMain_Paint(object sender, PaintEventArgs e)// Pain Function
        {
            graphics = this.CreateGraphics(); // Access to the graphic oject
            snake.Draw(graphics);
            food.Draw(graphics);
        }
       
        private void Update(object sender, EventArgs e)
        {
            this.Text = string.Format("Snake - score : {0}", score);// Hold the Name  and score
                snake.Move(direction);  // Call Direction
          for (int i = 1; i < snake.Body.Length; i++) // the Length body increase every time it eat food
                if (snake.Body[0].IntersectsWith(snake.Body[i]))// if hit the body it restart
                    Restart();
            if (snake.Body[0].X < 0 || snake.Body[0].X > 290) // if hit the maximum of the x axis it restart
                Restart(); 
            if (snake.Body[0].Y < 0 || snake.Body[0].Y > 190) // if it hit the maximum of the y axis it restart
                Restart();
            if (snake.Body[0].IntersectsWith(food.Piece)) // if it hit the piece 
            {
                score++; // the score increase
                snake.Grow();// The snake grow a leg
                food.Generate(rand);// The food spawn random


            }
            this.Invalidate(); // Repaint every frame

            


        }

        private void Restart()
        {
            gameLoop.Stop(); // Time stopped
            graphics.Clear(SystemColors.Control);// Clear the game
            snake = new Snake(); // set back to normal
            food = new Food(rand);// set back to normal
            direction = 0;// redo set back to normal
            score = 1;// redo set back to normal
            lblMenu.Visible = true;// redo set back to normal

        }
    }
}
