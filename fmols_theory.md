<!-- L'équation de départ est 
```math
y_{\displaystyle 1t}=c_{\displaystyle 1}+\tilde{y}_{2t}^\prime\tilde{\beta}+u_{1t},
```
avec $\tilde{y}_{2t}^{}$ un vecteur de $n-1$ variables I(1) et $c_1$ la constante du modèle. La statistique de test est construite après avoir estimé le modèle en suivant la procédure de Phillips et Hansen (1990) décrite dans Hansen (1992). Nous nous sommes appuyés sur la description faite dans ce dernier article dans le cas où l'équation de cointégration possède seulement pour composante déterministique une constante. Je donnerai les étapes d'estimation très bientôt :)


\begin{itemize}\item[(i)]{\textbf{Estimation du mod\`ele}.} On estime
l'\'equation ci-dessus et sauvegarde la s\'erie du r\'esidu dans
$\hat{u}_{1t}$, ainsi que les param\`etres estim\'es du mod\`ele
dans $\hat{\gamma}^\prime=(\hat{c}_1,\hat{\tilde{\beta}}^\prime)$;
\item[(ii)]{\textbf{Estimation du sous-mod\`ele des variables
explicatives}.} On prend les diff\'erences premi\`eres de la
s\'erie $\tilde{y}_{2t}$, i.e. $\Delta \tilde{y}_{2t}$ que l'on
sauve dans $\hat{u}_{2t}$. Notons que l'on perd une observation ;
\item[(iii)]{\textbf{Pr\'e-blanchiement}.} D\'efinit le vecteur
$\hat{u}_t\equiv(\hat{u}_{1t},\hat{u}_{2t}^\prime)^\prime$, centre
ce vecteur, et estime le mod\`ele vectoriel auto-r\'egressif
d'ordre 1 suivant $$\hat{u}_t=\phi\hat{u}_t+e_t.$$ Sauvegarde le
vecteur $n\times 1$ du r\'esidu estim\'e, $\hat{e}_t$, ainsi que
la matrice $n\times n$ du terme auto-r\'egressif, $\hat{\phi}$. On
perd une seconde observation;
\item[(iv)]{\textbf{Calcul du noyau quadratique (``kernel'')}.} On d\'efinit
la fonction suivante $$w(s/\hat{M})=\frac{25}{12\pi^2
(s/\hat{M})^2}\left\{\frac{\sin(6\pi[s/\hat{M}]/5)}{6\pi[s/\hat{M}]/5}-
\cos(6\pi[s/\hat{M}]/5)\right\},$$ et
$$\hat{M}=1.3221(4(T-2)\alpha(2))^{1/5},$$ avec
$$\hat{\alpha}(2)=\sum_{j=2}^n\frac{4\hat{\rho}_j ^2\hat{\sigma}_j
^4}{(1-\hat{\rho}_j)^8}/\sum_{j=2}^n\frac{\hat{\sigma}_j
^2}{(1-\hat{\rho}_j)^4},$$ et enfin, $\hat{\rho}_j$ est le
coefficient estim\'e du terme auto-r\'egressif issu de la
r\'egression de $\hat{e}_{jt}$ sur $\hat{e}_{jt-1}$, et
$\hat{\sigma}_j$ est l'\'ecart-type estim\'e du r\'esidu de cette
r\'egression. La fonction $w(.)$ est appel\'ee \textbf{noyau} ou
fonction de pond\'eration et $\hat{M}$ \textbf{le param\`etre de
bande}. Des explications suppl\'ementaires sur les motivations de
l'utilisation de $w(s/\hat{M})$ sont expos\'ees dans Hansen (1992)
et Haug (1996, pp. 93-94);
\item[(v)]{\textbf{Matrice de variance-covariance de long-terme}.}
On utilise cette fonction afin de calculer
$$\hat{\Lambda}_e=\sum_{j=0}^{T-2}w(j/\hat{M})\frac{1}{T-2}
\sum_{t=j+1}^{T-2}\hat{e}_{t-j}\hat{e}_t ^\prime,$$
$$\hat{\Omega}_e=\sum_{j=1}^{T-2}w(j/\hat{M})\frac{1}{T-2}
\sum_{t=j+1}^{T-2}(\hat{e}_{t-j}\hat{e}_t
^\prime+\hat{e}_t\hat{e}_{t-j}^\prime)+\frac{1}{T-2}\sum_{t=1}^{T-2}
\hat{e}_t\hat{e}_t ^\prime ;$$
\item[(vi)]{\textbf{Recoloration}.} \`A partir des deux matrices
ci-dessus on cr\'ee les matrices recolor\'ees
$$\hat{\Lambda}=(I_n-\hat{\phi})^{-1}\hat{\Lambda}_e(I_n-\hat{\phi}^
\prime)^{-1}-(I_n-\hat{\phi})^{-1}\hat{\phi}\hat{\Sigma},$$ o\`u
$$\hat{\Sigma}=\frac{1}{T-2}\sum_{t=1}^{T-2}\hat{e}_t\hat{e}_t
^\prime,$$ puis
$$\hat{\Omega}=(I_n-\hat{\phi})^{-1}\hat{\Omega}_e(I_n-\hat{\phi}^
\prime)^{-1} ;$$ \item[(vii)]{\textbf{Partition}} \'Etant donn\'e
les dimensions de $\hat{\Lambda}$ et $\hat{\Omega}$, nous pouvons
partitionner ces deux matrices comme suit en faisant figurer les
dimensions de chaque bloc entre paranth\`eses :
$$\hat{\Lambda}=\left(\begin{array}{cc} \underset{(1\times
1)}{\hat{\Lambda}_{11}} & \underset{1\times
(n-1)}{\hat{\Lambda}_{12}}\\ \underset{(n-1)\times
1}{\hat{\Lambda}_{21}} &
\underset{(n-1)\times(n-1)}{\hat{\Lambda}_{22}}\end{array}\right),$$
$$\hat{\Omega}=\left(\begin{array}{cc} \underset{(1\times
1)}{\hat{\Omega}_{11}} & \underset{1\times
(n-1)}{\hat{\Omega}_{12}}\\ \underset{(n-1)\times
1}{\hat{\Omega}_{21}} &
\underset{(n-1)\times(n-1)}{\hat{\Omega}_{22}}\end{array}\right).$$

On ne s'int\'eresse pas \`a tous les blocs de ces matrices. On
calcule le scalaire suivant
$$\hat{\Omega}_{1.2}=\hat{\Omega}_{11}-\hat{\Omega}_{12}
\hat{\Omega}_{22}^{-1}\hat{\Omega}_{21},$$ et la matrice de
dimesnion $(n-1)\times 1$ suivante
$$\hat{\Lambda}_{21}^{+}=\hat{\Lambda}_{21}-\hat{\Lambda}_{22}
\hat{\Omega}_{22}^{-1}\hat{\Omega}_{21},$$ o\`u l'on remarquera
que $\hat{\Omega}_{1.2}$ est en fait l'\'el\'ement haut gauche de
l'inverse de $\hat{\Omega}$; \item[(viii)]{\textbf{Variable
d\'ependente transform\'ee}} Pour chaque observation de la
variable d\'ependente $y_{1t}$, on cr\'ee une nouvelle variable
d\'ependente not\'ee
$y_{1t}^{+}=y_{1t}-\hat{\Omega}_{12}\hat{\Omega}_{22}^{-1}\hat{u}_{2t}$,
avec $\hat{u}_{2t}$ tel que d\'efinit dans (ii). Nous pouvons
enfin obtenir un \textbf{estimateur pleinement modifi\'e}
$\hat{\gamma}^{+}$ du vecteur des param\`etres $\tilde{\gamma}$,
$$\hat{\gamma}^{+}=(M_{TT})^{-1} (\sum_{t=1}^{T-2}y_{1t}^{+}z_t
^\prime)-(M_{TT}^{-1}\left(
\begin{array}{c}\underset{(1\times 1)}{0}\\ {\hat{\Lambda}_{21}^{+}}
\end{array}\right),$$ avec $z_t=(1\
\tilde{y}_{2t}^\prime)^\prime$ et $M_{TT}=\sum_{t=1}^{T-2}z_t z_t
^\prime$.
\end{itemize}

\begin{center}\textbf{Section 2, Routine de calcul de la
statistique $\mathbf{L_c}$}\end{center} Nous avons sp\'ecialement
d\'evelop\'e un programme pour le calcul de la statistique $L_c$,
que nous avons appliqu\'e au test de stabilit\'e de l'\'equation
de demande sur le march\'e des non V.Q.P.R.D. Le programme a
\'et\'e \'ecrit sous le logiciel d'\'econom\'etrie Rats. Il est
disponible sur demande \`a l'auteur. Une version plus simple de ce
programme, appliqu\'ee \`a une paire de s\'eries consid\'er\'ee
par Hansen (1992), se trouve sur le site internet officiel de la
maison d'\'edition du logiciel Rats \`a l'adresse
\url{www.estima.com/procs_estimate.shtml}. -->
