# generate-2D-quadrilateral-mesh-with-neural-networks-and-tree-search

## File Description

This repository contains the single-threaded TreeMesh code:

nearly best meshes - state-of-the-art meshes generated by TreeMesh

MCTS*.ipynb - Monte-Carlo tree search (a brute force search algorithm); * here has a format of xx.xx.xxxx[x] (date + version number)

PPO*.ipynb - Proximal Policy Optimization (a deep reinforcement learning algorithm); * here has a format of xx.xx.xxxx[x] (date + version number)

Trueseed*.txt - initial boundary coordinates

1. \* == 0: seed-density-changing rectangle
2. \* == 1: pentagonal plate

delete*.bat - initialization tools

----------

## Tutorial

At present, you can run the program on old boundaries to reappear my results in the paper, or run the program on new boundaries with only a few extra steps! Check out the steps below. Skip step 1 and 2 if you only want to play with old boundaries.
 
1. Open the latest version folder. You need to input the new boundary (coordinates and density information) to [Coordinate.txt] and then run [Initialization.ipynb]. It will automatically generate the coordinates of all points. Currently we cannot convert .inp file, so you need to input manually.
2. A full [Coordinate.txt] contains information of one outer boundary and many inner boundaries (only exists if there are holes). Each boundary starts with a string "XBJ" with a number. The number is 0 for the outer boundary, and it increases 1 in turn. The following lines contains coordinates of points that are on the boundary (mostly they are vertexes) and the unit length between the current and the next point. It's worth mentioning that the outer boundary points shall be clockwise, while points on inner boundaries shall be anti-clockwise. Below is an example of a rectangular boundary with three square holes:
XBJ 0
0 0 1
0 7 1
6 7 1
6 0 1
XBJ 1
2.5 1 1
3.5 1 1
3.5 2 1
2.5 2 1
XBJ 2
2.5 3 1
3.5 3 1
3.5 4 1
2.5 4 1
XBJ 3
2.5 5 1
3.5 5 1
3.5 6 1
2.5 6 1
![alt text](https://github.com/gt2001/generate-2D-quadrilateral-mesh-with-neural-networks-and-tree-search/blob/main/123.png?raw=true)
4. Open the latest version folder, and open [PPO.ipynb], scroll down to the penultimate code box that defines all hyper-parameters.
5. R
6. 
----------

## Contributions

Paper draft link (arXiv): https://arxiv.org/abs/2111.07613

Present performance:

Pentagonal plate: 0.9106 (5.3204% better than ABAQUS: 0.8646, 1.4822% better than FreeMesh-S: 0.8973)

Seed-density-changing rectangle: 0.8011 (13.8573% better than ABAQUS: 0.7036)

----------

## Update Log

This is a long-term on-going project. New updates will be written here (e.g. code updates, .pdf meshes, and .pdf reports). Please do not distribute these files to other websites.

11.13.2021[0]: Completed the original version of single-threaded TreeMesh (this version is released).

11.19.2021[1]: Fixed the problem in [delete.bat] that does not delete record text files every time.

11.20.2021[2]: Added the force-choice mechanism in [PPO.ipynb] that gives the agent 2 chances to choose type 0 in an episode. This also leads to a higher search efficiency in [MCTS.ipynb].

11.20.2021[3]: Added an input box before launching [delete.bat] in [PPO.ipynb] to avoid deleting/replacing records by mistake.

11.28.2021[4]: Optimized [PPO.ipynb] to accelerate calculation speed.

11.28.2021[5]: Updated [MCTS.ipynb] to fit the new mechanism in [PPO.ipynb] (this version is released).
