# generate-2D-quadrilateral-mesh-with-neural-networks-and-tree-search
I'm Hua Tong, a senior student at University of Science and Technology of China, majoring in Theoretical and Applied Mechanics. This repository contains the single-threaded TreeMesh code:

MCTS.ipynb - Monte-Carlo tree search (a brute force search algorithm)

PPO+workers+GAE+2output.ipynb - Proximal Policy Optimization (a deep reinforcement learning algorithm)

This is a long-term on-going project. New updates will be written here (e.g. .eps files, .pdf reports). Please do not distribute these files to other websites.

Paper draft link (arXiv): https://arxiv.org/abs/2111.07613

Present performance:

Pentagonal plate: 0.9106 (5.3204% better than ABAQUS: 0.8646, 1.4822% better than FreeMesh-S: 0.8973)

Seed-density-changing rectangle: 0.8011 (13.8573% better than ABAQUS: 0.7036)

---------- Update log ----------

11.19.2021: Fixed the problem in [delete.bat] that does not delete record text files every time.

11.20.2021: Added the force-choice mechanism in [PPO+works+GAE+2output.ipynb] that gives the agent 2 chances to choose type 0 in an episode. This also leads to a higher search efficiency in [MCTS.ipynb].
