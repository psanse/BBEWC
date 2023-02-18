This folder contains a linux binary release for the exact algorithm BBECW for the maximum edge weighted clique problem.

Article: A new branch-and-bound algorithm for the maximum edge-weighted clique problem. Eur. J. Oper. Res. 278(1): 76-90 (2019)

https://www.sciencedirect.com/science/article/pii/S0377221719303054


Date of release@18/02/2023
Compiled with Ubuntu 16.04.7 LTS

%%%%%%%%%%%%
%%
%% INSTRUCTIONS
%%
%%%%%%%%%%%

Run the binary from the command line with the following parameters: name of the graph (in DIMACS format), time limit (in seconds), vertex-ordering parameter (0-NONE, 1-DEG-SORT) and a lower bound:



./BBECW_20231802 <filename> <time limit> <sort_type> <lower bound>



BBECW currently considers  the vertex orderings from the literature: DEG-SORT (based on vertex degree). When the graphs are large or massive, the current implementation of DEG-SORT can take time (use sorting parameter 0 for these cases).

The current release of BBECW is limited compared with the published paper; it does not use a strong initial heuristic to determine an initial lower bound and only works with integer weights. Thus, the reported results in the above referred paper may vary.


%%%%%%%%%%%%
%%
%% EXAMPLE
%%
%%%%%%%%%%%

Typing: 

./BBECW_20231802 brock200_1.clq 100 1 1500  

selects the DEG-SORT ordering of vertices and times out if the instance brock200_1.clq  is not solved within 100s using 1500 as an initial lower bound.


The resulting output is: 

*****************************
DATA:/media/datos/graphs/edge_weight_selection/brock200_1.clq    N:200   M:14834         D:0.745427
TIME_LIMIT:100
TIME_LIMIT_HEUR:-1
ALG:1
SORTING:1
AMTS:0
LB in CML: 1500
*****************************

parsing....
preprocessing....
w:[8507,1490548]
solving....
199 197 195 196 192 186 183 170 164 155 179 144 137 76 [14][8689]:8689
199 197 195 196 192 186 183 170 164 155 137 116 144 18 76 [15][9951]:9951
199 197 195 196 192 186 183 170 164 155 137 116 38 76 18 [15][10159]:10159
199 197 195 196 192 186 183 170 164 137 116 76 38 158 17 [15][10487]:10487
199 197 195 196 192 186 183 170 164 137 116 76 38 18 17 [15][10593]:10593
199 197 195 196 192 186 170 164 155 137 116 97 76 38 18 [15][10631]:10631
199 197 195 196 192 186 170 164 137 116 97 76 38 158 17 [15][10759]:10759
199 197 195 196 192 186 170 164 137 116 97 76 38 18 17 [15][11065]:11065
199 197 195 192 186 183 175 167 144 116 99 76 65 24 18 14 [16][11455]:11455
199 197 195 192 186 170 167 155 144 116 80 76 65 18 14 2 0 [17][12104]:12104
199 197 195 192 186 170 155 116 97 80 65 38 18 14 2 76 0 [17][13168]:13168
199 197 195 186 140 137 130 97 77 65 39 29 24 38 158 76 0 [17][13840]:13840
199 197 195 186 140 137 130 97 77 65 39 29 24 38 23 76 0 [17][14048]:14048
199 197 195 186 140 137 130 97 77 65 39 29 24 38 23 3 0 [17][14176]:14176
199 197 182 175 161 144 139 110 109 96 91 41 24 94 20 8 4 1 [18][15065]:15065
199 197 182 175 161 144 139 110 109 96 91 41 24 19 20 8 4 1 [18][15439]:15439
199 197 144 140 109 68 67 96 65 39 32 25 24 4 3 2 1 0 [18][15993]:15993
199 197 144 109 96 68 67 65 39 32 25 24 8 4 3 2 1 0 [18][16001]:16001
199 192 182 168 167 163 161 129 113 111 108 107 76 56 53 41 24 14 17 [19][17775]:17775
199 189 161 146 144 139 113 53 52 41 32 31 28 24 19 14 12 4 1 0 [20][18247]:18247
193 184 182 179 177 170 169 163 140 130 128 124 109 96 78 75 68 54 49 22 20 [21][21230]:21230
[w:21230,23.2949s]
checking solution...

*****************************
DATA:/media/datos/graphs/edge_weight_selection/brock200_1.clq    N:200   M:14834         D:0.745427
TIME_LIMIT:100
TIME_LIMIT_HEUR:-1
ALG:1
SORTING:1
AMTS:0
LB in CML: 1500
*****************************
*****************************
w:21230 t_par: 1.8e-05  t_pp: 0.002411  t_search: 23.2948
*****************************
133 135 84 38 101 67 149 91 134 141 89 92 80 17 177 86 185 93 107 72 19  [21]


In addition, the file "info_clique_ew.txt" is created with the following information:

<instance name> <n> <m> <time_limit> <sorting_choice> <LB_preproc> <LB_command_line> <omega_we>
<tparse> <tpreproc> <tsearch> <is_time_limit> <#calls>

In this case the output is 
<path>brock200_1.clq	200	 14834	100	  1	 8507	1500	21230	1.8e-05 	0.002411	23.2948 	0 	1333365	

