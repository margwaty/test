\documentclass[a4paper]{article}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[english]{babel}
\usepackage[hyphens]{url}
\usepackage[pdftex,urlcolor=black,colorlinks=true,linkcolor=black,citecolor=black]{hyperref}
\usepackage{csquotes}
\usepackage{fourier}
%\usepackage[sort]{natbib}
\usepackage{geometry}
\usepackage{array}
\usepackage{multirow}
\usepackage{float}
\usepackage{hyperref}

% Indication of to-dos
\usepackage{color}
\newcommand{\todo}[1]{\noindent\textcolor{red}{{\bfseries \{TODO}: #1{\bfseries \}}}}

% examples
\newcounter{example}
\newenvironment{example}[1][]{\refstepcounter{example}\par\medskip\noindent%
   \textbf{Example \theexample #1.} \rmfamily}{\medskip}
   
% verbatim in box
\usepackage{fancyvrb}

% good maths
\usepackage{amsmath}

% bold maths
\usepackage{bm}

\title{How hot is \texttt{.brussels}? \\Analysis of the uptake of the \texttt{.brussels} top-level domain name extension}
\author{
  Margot Waty\thanks{Corresponding author}\\
  Université libre de Bruxelles (ULB)\\ 
  Information Science Department \\ 
  Avenue F.D.\,Roosevelt\,50 -- CP\,123 \\ 
  B-1050 Brussels, Belgium \\ 
  \href{mailto:margwaty@ulb.ac.be}{margwaty@ulb.ac.be}
  \and  Seth van Hooland\\
  Université libre de Bruxelles (ULB)\\ 
  Information Science Department \\ 
  Avenue F.D.\,Roosevelt\,50 -- CP\,123 \\ 
  B-1050 Brussels, Belgium \\ 
  \href{mailto:svhoolan@ulb.ac.be}{svhoolan@ulb.ac.be}
  \and Simon Hengchen\\
  Université libre de Bruxelles (ULB)\\ 
  Information Science Department \\ 
  Avenue F.D.\,Roosevelt\,50 -- CP\,123 \\ 
  B-1050 Brussels, Belgium \\ 
  \href{mailto:shengche@ulb.ac.be}{shengche@ulb.ac.be}
  \and Mathias Coeckelbergs\\
  Université libre de Bruxelles (ULB)\\ 
  Information Science Department \\ 
  Avenue F.D.\,Roosevelt\,50 -- CP\,123 \\ 
  B-1050 Brussels, Belgium \\ 
  \href{mailto:mcoecke@ulb.ac.be}{coecke@ulb.ac.be}
}
\date{}

\begin{document}
\maketitle

\begin{abstract}
The opening up of the top-level domain name market since 2013 has offered new perspectives
for companies, administrations and individuals to include within the domain name of their website a geographic component.
Little to no research has been carried out since then to analyse the uptake of the new top-level domain names. 
Based on the case of \texttt{.brussels}, this article proposes an in-depth study of the new domain names which have
been registered since XXX with the new top-level domain name. By making use of freely available software tools such as
OpenRefine and Natural Language Processing (NLP) methods, the entire corpus (6300 domain names) was analysed from
a quantitive perspective. Based on a statistically representative sample, a qualitative interpretation has led to the development
of a typology of the recently registered domain names. By doing so, the article gives a detailed insight in the impact of the recent
changes of the rules concerning domain name registration. Researchers, policy makers, investors and everyone who cares about
the Brussels identify in the digital realm can gain through the analysis a better understanding of the state of play of top-level domain
name registration. 
\end{abstract}

\section{Introduction}
Real estate professionals often say there are three important qualities to take into account when investing in a house: the location, the location and the location. We could not agree more: domain names are the cornerstone of our digital economy. The analogy with the housing market does not stop there. Just as you permanently need to invest in a house (from minor maintenance such as polishing wooden floors to major renovation of the roof, for example), the investment in a URL does not stop at acquiring a domain name. Commercial parties are very much aware of the future importance of URLs, illustrated by practices such as the domain name aftermarket where URLs are bought and sold by commercial parties. The current hype surround the Internet of Things and Linked Data will only emphasise the importance of stable and
meaningful domain names.

Why is the case of \texttt{.brussels} interesting to study? Compared to many of the other newly created TLDN,
such as \texttt{.music} or \texttt{.photography}, the range of usages is potentially a lot wider. Even when
compared with other geographic TLDN relating to city names, such as \texttt{.gent} for example, the eight letter
term \enquote{Brussels} is being used in a large variety of contexts.
This aspect makes the analysis of its uptake particularly intriguing,
as the list of the URLs allows us for example to forecast future investments
or how the term Brussels is being used within a city marketing strategy. 

After a short introduction to the complex world of domain name registration,
the article will introduce the case-study and detail which methods
have been used to perform both the quantitative and qualitative analysis. 

\section{Quick and rough guide to the domain name market place}
\todo{Margot, tu peux écrire environ 3 pages sur l'histoire et l'évolution de l'enregistrement
des noms de domaine? }

Tous les jours, nous tapons dans nos navigateurs des dizaines de noms de domaine sans même nous rendre compte de leur
fonction et des mécanismes qui rendent l’accès à une page web possible.
Ces mécanismes sont en partie régis par le Domain Name System (DNS), où les noms de domaine correspondent à des adresses IP,
identifiants uniques sur Internet. Afin de mieux comprendre le rôle du DNS ainsi que l’impact majeur 
que les noms de domaine ont sur l’image que l’on se forge en ligne, il est indispensable de faire un 
léger détour par ses fondements.

\subsection{Les adresses IP : identificateurs uniques sur Internet}

L’efficacité de la communication et de l’échange de données dépend du langage commun utilisé à son effet. 
Cela vaut pour les êtres humains comme pour tout autre être vivant, mais également pour les systèmes informatiques. 
Faire appel à un certain nombre de règles et de procédures prédéfinies afin de permettre la communication, c’est élaborer un
standard commun, un protocole de communication. 
Pour communiquer, un émetteur doit également être capable d’identifier le récepteur grâce à une caractérisation unique. 
Tel que l’ADN représente l’identifiant naturel qui distingue chaque être vivant d’un autre, 
le concept d’identifiant unique peut être assigné à tout élément singulier dans l’univers. Ce sont ces deux concepts,
protocole de communication et identifiants uniques, qui se retrouvent à l’origine de l’échange de données sur Internet. 
En effet, les différents constituants des réseaux qui composent Internet, communiquent entre eux grâce à l’utilisation 
de la suite de protocoles TCP/IP et s’identifient par leurs identifiants uniques, les adresses IP 
(représentées par une série de chiffres entiers\todo{simon: pour IPv4. IPv6 a aussi des lettres}). 
Le procédé d’échange, s’effectue quant à lui, sur base du modèle de commutation par paquet (Packet Switching). 
Selon ce modèle, les données sont fractionnées et transmises en plusieurs morceaux, ou "paquets", 
d’un hôte à l’autre du réseau. Chaque partie d'information transmise se voit assigner une "étiquette" contenant 
les informations nécessaires afin d'arriver à destination. Parmi ces informations, on retrouve l’adresse IP 
de l’instance destinatrice (l’hôte destinataire).

Si chaque objet connecté à Internet se voit assigner une adresse IP, il est important de préciser que ce 
n'est pas de l'adresse de la "machine" sur le réseau dont il s'agit, mais bien d'une adresse d'interface réseau. 
Un objet peut se voir assigner plusieurs adresses IP, si celui-ci est connecté à différents réseaux, et dispose ainsi de
plusieurs interfaces. L’essentiel c’est que chaque entité puisse être identifiée de manière singulière dans l’environnement
dans lequel elle s’insère. Rappelons que c’est ce caractère « unique » d’identification qui est à l’origine de tout système
d’échange cohérent.

L’unicité implique inévitablement une certaine coordination. Tel que le mentionne Milton L. Mueller dans 
son ouvrage Ruling the Root, la coordination d’identifiants uniques s’effectue sur deux niveaux distincts. 
Tout d’abord, il faut définir un espace commun d’adressage (ou de nommage) où une série de valeurs doivent être déterminées
comme norme commune pour l’attribution d’identifiants uniques. 
Ensuite, il faut pouvoir attribuer ces valeurs uniques aux dispositifs ou utilisateurs dans l’espace défini, de manière exclusive. 

Si la définition d’un espace commun s’est fait sur base de la suite de protocoles TCP/IP, 
qui est devenu un standard de part son développement et son acceptation tacite, 
le processus d’attribution des identifiants uniques, adresses IP, est quant à lui bien plus complexe qu’il n’en a l’air. 
En effet, ce deuxième niveau de coordination a des répercutions sur trois dimensions: technique, politique et économique.

\subsection{Coordination de l’attribution d’identifiants uniques sur Internet}

Association de noms aux adresses IP

Lors du développement des premiers réseaux d’échanges de données et, ainsi, de l’Internet, l’instance initiatrice du projet,
l’Advanced Research Projects Agency (ARPA) (agence du Département de la Défense Américaine) n’imaginait pas l’étendue et la
vitesse à laquelle ces réseaux allaient se développer. A l'origine, c'était le docteur Jon Postel de l’Université de
Southern California’s Information and Science Institute (ISI) qui assumait la délicate tâche d’assigner des adresses IP aux
premières entités liées aux réseaux utilisant la suite de protocole TCP/IP. Dans les années 80', il y avait encore peu
d'ordinateurs reliés aux différents réseaux rendant l'attribution manuelle d'adresses IP encore possible.

Toutefois, le besoin se faisait ressentir d'assigner des noms à ces adresses composées de chiffres pour des questions de
facilité. En effet, l’attribution de noms aux adresses IP offre deux grands avantages. Tout d'abord, cela permet de
faciliter la mémorisation des adresses. Il est évident que www.google.com est plus facile à retenir que 74.125.195.94.
Ensuite, l'attribution de noms facilite la modification des adresses IP. On peut désormais modifier celle-ci sans pour
autant changer le nom qui lui était attribué. On ne doit donc plus  communiquer l’adresse modifiée, car son nom reste
inchangé.

À l'époque, c'était un Network Information Center (Organisme qui gère des réseaux informatiques) qui maintenait un fichier
texte ("host.txt"), composé de tables de traduction des noms en adresses IP. Chaque table se présentait sous forme d'un
fichier séquentiel ou chaque ligne renvoyait à l'adresse IP d'une machine et le nom d'hôte qui y était associé. Cette tâche
de traduction fut facilitée suite à l'arrivée de name servers au sein des différents réseaux. En effet, ces name servers
(bases de données spécialisées) se chargent de traduire les noms par leur adresse IP correspondante et vice versa. Lors
d'une recherche, un hôte pourra trouver une ressource en interrogeant un name server présent sur le réseau. Ces derniers
facilitent la gestion au sein des réseaux et les rendent plus dynamiques et réactifs aux changements.

Au fil du temps, la taille grandissante des réseaux, et le nombre croissant de noms associés aux adresses IP, ont fait
apparaître trois grands problèmes:
\begin{itemize}
\item lié à l'organisation: retrouver une information souhaitée (nom ou adresse IP) au sein de la base de données devenait de
plus en plus lent, suite au nombre croissant de données qui y étaient présentes. Une méthode d'indexation ou d'organisation
des noms devenait nécessaire;
\item à la flexibilité: si tous les hôtes voulaient questionner un name server, le poids de téléchargement devint trop élevé.
Il fallait trouver une manière d'épandre les téléchargements sur plusieurs name servers;
\item lié à la gestion: avec un nombre d'enregistrements élevé, ainsi que des mises à jour s'effectuant de manière simultanée sur
la base de données, la gestion devint très complexe. On ressentit le besoin de séparer l'administration de l'enregistrement
des ressources (des noms).

\end{itemize}


Afin de pallier ces trois préoccupations, des scientifiques de l’Information Science Institute (de l'Université de Southern
California(USC)) spécialisée dans le développement des technologies de l'information et de la communication, dont Jon Postel
et Paul Mockapetris, créèrent le système de nom de domaine (DNS) en 1983.

\subsection{Le Domain Name System (DNS)}

Le système des noms de domaine est une implémentation optimisée du concept de name server sur Internet, respectant ses
conditions préexistantes. Il répond aux trois problématiques ayant fait surface lors du développement des réseaux 
informatiques: le besoin de hiérarchisation, la répartition des téléchargements sur plusieurs serveurs et la nécessité de
déléguer
l'administration des name servers. Le DNS repose sur une structure arborescente composée de différentes « zones », renvoyant
vers différentes portions de l’espace de nommage («namespace»).
La zone dite «racine» est la zone unique se situant au sommet de toute la hiérarchie. Elle est représentée par un point 
(« . »), également connu sous le nom de «silent dot». En effet, malgré le fait qu’il devrait être visible, le dernier point
est souvent omis. 
Cette première zone est suivie d’une seconde zone regroupant les Top-Level Domains (TLD). Les TLDs se divisent selon deux
catégories: les generic Top Level Domains (tels que : .com, .org, .int, .edu, .mil, .gov, .net, etc.) et le country code Top
Level Domains (tels que : .be, .fr, .us, .jp, etc.).
La première catégorie se caractérisait, à l’origine, seulement par des domaines d’activités (par exemple, l'extension ".edu"
se rapporte au domaine de l'éducation) alors que la seconde catégorie se base, encore aujourd'hui, sur la localisation
géographique. 
La zone des Top Level Domains est ensuite suivie d'une zone contenant des Second Level Domains (SLD) et ainsi de suite.

L’autorité gérant le domaine Racine, contrôle quels noms de domaine de premier niveau sont visibles dans le "namespace".
Elle peut également choisir quel serveur reçoit l’autorité sur ces noms de domaines. Il est donc évident que l’entité qui
contrôle cette zone contrôle l’ensemble du système. En effet, chaque nom du système est assigné à une autorité qui sera
responsable de l'administration de celui-ci et de sa gestion. L’entité responsable d'un nom pourra à son tour déléguer
l'autorité des entités inférieures à la sienne, selon la hiérarchie des noms de domaine.

\subsection{De la gestion du DNS à la création de l’ICANN}

À l'origine, l'autorité sur le domaine racine était exercée par Jon Postel, sous contrat avec le gouvernement américain.
L’enregistrement des domaines de second niveau sous les gTLD, était assumé par la Stanford Research Institute (SRI),
également sous contrat avec le Département de la Défense américaine. Toutes ces activités, dirigées par Jon Postel, furent
ensuite regroupées sous l’Internet Assigned Number Authority (IANA). Par la suite, le SRI fut remplacé par la société privée
Network Solutions, Inc (NSI, aujourd’hui Verisign). L’IANA délégua la gestion des différents ccTLD aux pays concernés. La
gestion des gTLD fut, quant à elle, administrée à une série d'organisations ("registries") qui, pour la majorité, sont
étroitement liées au pouvoir Américain. En effet, la plupart des gTLD sont rapidement accaparés par les Etats-Unis grâce à
leur mainmise sur le NSI et l’IANA via différents contrats.

Rappelons qu'initialement, les gTLD sont liés à des domaines d’activités, le «.com» désignant, par exemple, une fonction
commerciale. Ceux-ci touchent donc un plus grand nombre d’utilisateurs que les ccTLD. Par conséquent, la gestion de cette
première catégorie permet un contrôle plus global sur Internet et le monopole de gestion des gTLD par les Etats-Unis dérange.
Au milieu des années 90’, plusieurs inquiétudes obligèrent Jon Postel et le gouvernement américain à repenser la politique
du DNS. Premièrement, l’autorité de l’IANA reposait sur une seule personne. S’il arrivait quelque chose à Jon Postel, qui
lui succéderait à la gouvernance du DNS? Deuxièmement, l’émergence d’entrepreneurs voulant entrer en compétition avec le 
NSI, par la création de namespaces alternatifs, de nouveaux TLDs et des registres indépendants, ils menaçaient de fragmenter
tout le système mis en place.

La position centrale de l’IANA sur Internet suscitait également une certaine envie de la part d’autres organisations et
gouvernements (des organisations telles que l’Union internationale des télécommunications, différents gouvernements
nationaux ou encore la Commission européenne). Ces derniers se sentirent menacés par l’emprise des Etats-Unis sur cette
nouvelle infrastructure mondiale d’échange d’informations qu’est Internet. Fin des années 90’, l’appréhension du 
gouvernement américain face à ces tensions incita celui-ci à constituer un groupe de travail composé de différentes
institutions et organisations afin de trouver des solutions.
L’idée était de réorganiser l’IANA en une entité privée, plus légitime, dans le but de représenter la communauté Internet
dans son ensemble.

C’est ainsi qu’après plusieurs mois de modifications et de débats, le gouvernement américain présenta en 1998 
le White Paper, acte de naissance de l’Internet Corporation for Assigned Names and Numbers (ICANN). Jon Postel décéda un
mois après la création de celle-ci en septembre 1998.

l’ICANN et les generic Top Level Domains

L'ICANN est créée le 18 septembre 1998 et gère depuis lors le Domain Name System. Selon les objectifs décrits dans le 
"White Paper », on constate que le rôle de l’ICANN s’étant sur une dimension technique, économique et politique. 
Tout d’abord, l’ICANN englobe l’IANA et le NSI, c’est-à-dire la coordination de l’attribution unique de noms de domaine et
d’adresses IP. Ensuite, elle établit les règles et procédures de gestion et d’administration de l’espace de nommage afin
d’assurer son bon développement. Pour finir, les noms de domaine étant porteurs d’une valeur sémantique considérable, ils
peuvent être sujets à des conflits d’acquisition. Ayant l’autorité sur l’ensemble du DNS, l’ICANN peut décider de la manière
dont ces litiges doivent être traités.

Si l'ICANN est au centre des controverses pour sa gestion et son rôle sur Internet, elle est également sujette à de nombreux
débats quant à sa façon de gérer les generic Top Level Domains. En effet, elle a toujours été préoccupée de savoir quand,
comment et sous quelles circonstances de nouveaux gTLD pourraient être ajoutés.

Rappelons que le DNS a pour objectif d’offrir un système clair et simple pour catégoriser l’information et localiser des
activités sur Internet. Afin de maintenir une certaine stabilité, les adresses IP peuvent se voir transformer tout en
conservant les noms qui leur sont associés. Les noms de domaine sont donc perçus comme de réels points de références.
En étant de plus en plus associés à des produits et des services, ils dépassent leur simple rôle de localisateur pour
devenir de réels enjeux commerciaux, les noms de domaine deviennent des marques déposées. Cette mutation de fonction ne
s’est pas réalisée sans encombre. En effet, celle-ci a généré de nombreux conflits qui n’ont cessé de croître avec 
l’expansion du réseau et la croissance de l’enregistrement des noms de domaine.

Quatorze ans après sa création, l’ICANN décide de lever la contrainte liée à la limitation du nombre de gTLD. Le 13 juin
2012, elle a annoncé l'entrée de 1930 requêtes. Ce nombre est de loin supérieur aux 22 gTLD d’origine. Le même problème
survenu pour les domaines de seconds niveaux apparait à nouveau: l'intérêt commun pour un même nom de domaine. 
Sur l’ensemble des 1930 candidats, 230 gTLD ont été requis par plus de 751 candidats. Les demandes les plus populaires
concernaient le «.APP», «.HOME», «.INC» et le «.ART». Lorsqu’un nom de domaine est convoité par plusieurs acquéreurs de
légitimité égale, deux possibilités sont avancées. Ou ces derniers règlent le conflit entre eux, ou une enchère est
organisée et le nom de domaine ira au plus offrant.

La vente et la maintenance des noms de domaine représentent une industrie de plusieurs millions de dollars. 
Cependant, peu d’études ont été menées sur les mérites effectifs d’une augmentation du nombre de gTLD. 
Cette carence est due à la structure économique inhabituelle du DNS ainsi qu’à la structure inhabituelle de réglementation
de l’ICANN.
...


\section{Case study: the uptake of the \texttt{.brussels} top-level domain name}
\todo{A faire ensemble}

% échantillon vs full dataset
% matching
% linguistic input : length vs language vs "é & e"
% ownership
% new vs adaptation (redirects?)
% mobile?

\subsection{Processing the full corpus}

Using OpenRefine, we have cleaned the corpus and exported a \texttt{*.csv} file consisting of two columns.
Each row contains the two same URLs, in different columns. 
We then created a shell script\footnote{All scripts are available at \href{http://howhotis.brussels}{howhotis.brussels}.} which takes the first argument as an input to the \texttt{curl} command, and then checks if the result of the \texttt{curl} command matches the second URL. 
If the result matches the second argument, it means the domain name is used as is -- either to host a website at that particular URL, or is parked --, if it doesn't, it means the domain name is being redirected.
The intention behind verifying redirections is to determine whereas \texttt{.brussels} domain names are widely used as main domain names, or if they are mostly used as a \emph{defense mechanism} against domain squatters. 
\todo{simon: introduire tableau avec statistiques}

Another interesting information about domain names is their owners. 
Do we see, as it is the case for real estate, conglomerates speculating on a range of domain names?
In order to determine this, we used the \emph{WHOIS}\footnote{https://en.wikipedia.org/wiki/WHOIS en attendant une meilleure source} protocol, a protocol used to \enquote{[query] databases that store the registered users of assignees of an Internet resource, such as domain name, (...)}\todo{ajouter référence correctement}.
For privacy and commercial reasons\todo{à vérifier}, most non-commercial tools and websites limit the number of queries a single user can make per day. 
We have found out that the limit for the \texttt{.brussels} TLD, using the latest Debian Jessie \emph{whois} client\footnote{The package is present by default on any Debian installation, and is available at https://packages.debian.org/source/jessie/whois}, was of 60 queries per day per IP.
In order to bypass that limitation and correctly query the data for our \todo{ajouter nombre exact} domain names, we split our original file into 99 60-domain name files and added the \texttt{whois} command to each line. 
The final files, that were launched from 99 separate IPs, bore that following structure: 
\begin{verbatim}
whois -H 0800flowers.brussels
whois -H 10.brussels
whois -H 1000.brussels
whois -H 100masters.brussels
whois -H 100percentbrussel.brussels
\end{verbatim}

The result of the WHOIS querying bore interesting results, as described hereunder: \todo{ajouter résultats}

%Length repartition of the domain name
% done on openrefine; create new column based on this column -> value.length() -> facet by length


\begin{table}[]
\centering
\label{longueur}
\begin{tabular}{cccc}
length & \multicolumn{1}{c|}{number} & \multicolumn{1}{l}{length} & \multicolumn{1}{l}{number} \\ \hline
8      & \multicolumn{1}{c|}{596}    & 22                         & 31                         \\
7      & \multicolumn{1}{c|}{585}    & 23                         & 25                         \\
6      & \multicolumn{1}{c|}{523}    & 24                         & 20                         \\
9      & \multicolumn{1}{c|}{471}    & 25                         & 16                         \\
10     & \multicolumn{1}{c|}{451}    & 26                         & 9                          \\
5      & \multicolumn{1}{c|}{414}    & 28                         & 9                          \\
4      & \multicolumn{1}{c|}{409}    & 30                         & 9                          \\
11     & \multicolumn{1}{c|}{362}    & 2                          & 8                          \\
3      & \multicolumn{1}{c|}{356}    & 32                         & 7                          \\
12     & \multicolumn{1}{c|}{307}    & 27                         & 6                          \\
13     & \multicolumn{1}{c|}{280}    & 29                         & 5                          \\
14     & \multicolumn{1}{c|}{207}    & 33                         & 3                          \\
15     & \multicolumn{1}{c|}{190}    & 34                         & 2                          \\
17     & \multicolumn{1}{c|}{153}    & 35                         & 2                          \\
16     & \multicolumn{1}{c|}{140}    & 37                         & 2                          \\
18     & \multicolumn{1}{c|}{105}    & 39                         & 2                          \\
19     & \multicolumn{1}{c|}{88}     & 31                         & 1                          \\
20     & \multicolumn{1}{c|}{76}     & 36                         & 1                          \\
21     & \multicolumn{1}{c|}{48}     & 38                         & 1                             
\end{tabular}
\caption{Length repartition of the domain names}
\end{table}

\subsection{Sampling}

\todo{max peux-tu relire ?}
In order to gain a more qualitative insight to the dataset, we set out to select a sample.
Basing our selection on a 99\% confidence score and an interval of 5, we randomly chose 592 domain names. 
The selection has been carried out randomly, as we were afraid variations of the same domain name -- for example, \texttt{fullglassrailing.brussels}, \texttt{full-glass-railing.brussels} and \texttt{full-glassrailing.brussels} -- would prevent proper representativeness if we took one domain name every \todo{nombre exact} domain names.
To do so, we created a python script\footnote{Available at \href{http://howhotis.brussels}{howhotis.brussels}} which added all domain names to a list, shuffled the list using the \texttt{random} python library and extracted the first 592 domain names of that list. 

\section{Discussion}
\label{ccl}

\section{Conclusions and future work}

\section*{Acknowledgements}

huginn \& muninn

%\newpage
\small
\bibliographystyle{apalike}
\bibliography{biblio}

\end{document}
