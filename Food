using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Drawing;

namespace WindowsFormsApplication1
{
    class Food
    {
        public Rectangle Piece; // The piece
        private int x, y, width =10, height = 10; // postion and size of the piece

        public Food(Random rand) { // call function
             
            Generate(rand); // call generate to give the position x and y 
            Piece = new Rectangle(x, y, width, height);  // assign x y, and size to the piece
        }

        public void Draw (Graphics graphics) // Graphic object
        {
            Piece.X = x; // assign position to draw for x
            Piece.Y = y; // assign position to draw for y
            graphics.FillRectangle(Brushes.Brown, Piece); ; // Draw the piece, and pick coor


        }

        public void Generate(Random rand) // Generate random position 
        {
            x = rand.Next(0, 30) * 10; // generate random position for x from 10 to 30
            y = rand.Next(0, 20) * 10; // generate random position for y from 10 to 20

        }
    }
}
