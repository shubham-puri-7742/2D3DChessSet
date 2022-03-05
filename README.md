# 2D3DChessSet
### A chess set that combines 3D pieces with Unicode symbols

This chess set is a 2-in-1 design that combines 3D chess pieces with Unicode symbols. As in a standard chess set, it consists of black and white pieces. Blue and red have been added as accent colours, although it is not required for the design to work.

The 'secret' behind the trick is Boolean intersection. The cuts on the pieces are not random as it may seem at first glance, but based on a projection of the Unicode symbol for the corresponding piece. The Unicode symbol works like a cookie cutter on full 3D models, cutting out the shapes required for the top (orthographic) view to look like the symbols would normally look in 2D chess.

Currently, this repo contains only the 3D model for the aforementioned chess set. Future work may include adding a simple renderer program to display these pieces (as opposed to showcasing renders generated using Blender Cycles).

### Reflection

This project emerged out of a knight model that I had worked on in 3DS Max. For the set, however, I switched to the open source Blender, and worked with the whole set instead of just the knight.

![ChessSetPlain3D](https://user-images.githubusercontent.com/86086833/155079566-a8794479-c9be-4cd8-8785-34e9c27bc32c.png)
##### Step 1: Simple 3D Chess Pieces

I began with modelling full 3D pieces as per the standard Staunton set design. I mainly used spline modelling, leveraging the radial symmetry of the pieces. The only exception was the knight, which could only use bilateral symmetry. The knight was simplified from my earlier knight design. I felt the simplification was necessary because the projection in the next step was expected to create some odd-looking cuts in the model.

![ChessSetMakingOfProjectionsOn3DPieces](https://user-images.githubusercontent.com/86086833/155079616-c4f435f3-f398-464c-b7be-140dc2c98f99.png)
##### Step 2: Unicode Symbols over 3D Pieces

The next step was creating meshes from text using the Unicode symbols for each piece. I used the FreeSerif font mainly for its neat symbols using only black and white (no greys), but it will be worthwhile to experiment with other fonts.

![ChessSetMakingOfProjecting2DSymbolsOn3DPieces](https://user-images.githubusercontent.com/86086833/155079664-6dce7bb6-86ac-4000-80d4-f136435d19f2.png)
##### Step 3: Taking the Intersection of the 2D Symbol Projections with the 3D Pieces

The final part, and the 'trick' that generates a 2-in-1 design, was taking the Boolean intersection of a projection of the symbol-meshes from the previous step with the corresponding 3D piece. Although not necessary, I chose to go with accent colours (red in the white pieces, blue in the black pieces) on the new faces that the intersection created.

The main challenge was positioning the Unicode symbol projections, because for the pieces to incorporate elements from both their 3D designs and the 2D symbols, the projections had to lie entirely within the circular bounds (the base of the piece when viewed from the top) of the piece so that the intersection (when viewed from the top) shows the entire symbol and not just a part of it, and yet be the largest possible size that would fit inside, or too much of the 3D piece would be cut on taking the intersection.

### Renders

(Currently using Blender Cycles, although I would aim to create a simple renderer from scratch sometime.)

#### 3D

![ChessSet3DPerspective1](https://user-images.githubusercontent.com/86086833/155076833-32645cde-e5bd-402c-b0d5-713ab2510787.png)
##### Perspective render 1 showing the 3D pieces. Note the white and black pieces with red and blue accents where the Unicode symbols made the cuts.

![ChessSet3DPerspective2](https://user-images.githubusercontent.com/86086833/155076867-47d28bab-a6ff-4c2f-ade7-ad096d865455.png)
##### Perspective render 2 showing the 3D pieces. Note the white and black pieces with red and blue accents where the Unicode symbols made the cuts.

![ChessSet3DPerspectiveWhitePieces](https://user-images.githubusercontent.com/86086833/155076885-94b5a4fa-b086-4cbe-a933-8238a3d109c0.png)
##### Perspective render of the white pieces.

![ChessSet3DPerspectiveBlackPieces](https://user-images.githubusercontent.com/86086833/155076897-005b7036-699f-4cb8-8e35-b0fa08e3d9ba.png)
##### Perspective render of the black pieces.

#### 2D

![ChessSet2DOrthographicLitGreyBG](https://user-images.githubusercontent.com/86086833/155076916-1409d139-a559-4837-a78e-0d246ed57ff8.png)
##### Orthographic top view render (lit) against a grey background. The soft shadow indicates that the render is indeed generated from the 3D pieces.

![ChessSet2DOrthographicUnlitBrownBG](https://user-images.githubusercontent.com/86086833/155076924-c263b959-cb50-4e21-859b-64b7bf388bba.png)
##### Orthographic top view render (unlit) against a brown background. Admittedly, the 2D icons really look the part when rendering in unlit mode, which is the only potential downside of this design.
