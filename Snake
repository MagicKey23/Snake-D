using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Drawing;
namespace WindowsFormsApplication1
{
    class Snake
    {
        public Rectangle[] Body;// The body of the snake that could hold multiples rectangle
        private int x = 0, y = 0, width = 10, height = 10; // start position
        public Snake()// The Snake main function
        {
            Body = new Rectangle[1];
            Body[0] = new Rectangle(x, y, width, height);

        }

        public void Draw() // Draw the body, as it increase
        {
            for (int i = Body.Length - 1; i > 0; i--)// Make sure the head of the snake is Body[0]

                Body[i] = Body[i - 1];// Keep the Body move right when change direction 

        }

        public void Draw(Graphics graphics)// Draw the rectangles
        {
            graphics.FillRectangles(Brushes.Blue, Body); // Draw the rectangle and assign its color

        }

        public void Move(int direction)  {  // movement of the snake
            Draw();
            switch (direction) // 0 right // 1 down // 2 left // 3 up
            {
                case 0:
                    Body[0].X += 10;
                    break;
                case 1:
                    Body[0].Y += 10;
                    break;
                case 2:
                    Body[0].X -= 10;
                    break;
                case 3:
                    Body[0].Y -= 10;
                    break;

            }
        }

        public void Grow()
        {
            List<Rectangle> temp = Body.ToList(); // Add the body array to a list, named temp
            temp.Add(new Rectangle(Body[Body.Length-1].X, Body[Body.Length-1].Y, width, height));// Add tail the snake, because [0] is the head, -1 give the snake tail
            Body = temp.ToArray(); // Assign the result to the Body
                


        }



    }
  

}
