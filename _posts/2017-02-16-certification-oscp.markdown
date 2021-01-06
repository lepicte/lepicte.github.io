---
layout: post
title:  "OSCP: une première étape"
date:   2017-02-17
category: Certification
excerpt_separator: <!--more-->
lang: fr
---
Bonjour à tous,
  
Premier article de l'année, cependant ces derniers temps furent bien remplis avec notamment le passage de l'[OSCP](https://www.offensive-security.com/information-security-certifications/oscp-offensive-security-certified-professional/). J'en profite donc pour écrire une petite revue sur cette certif en espérant partager des infos qui pourront vous être utiles.
<!--more-->
  
**Qu'est-ce que l'OSCP?**
  
![oscp]({{ site.url }}/public/images/oscp/oscp1.png)

L'OSCP est une certification en sécurité offensive (pentesting) délivrée par [Offensive Security](https://www.offensive-security.com/), acteur majeur de la scène infosec puisqu'ils sont derrière plusieurs projets comme la distribution [Kali](https://www.kali.org/), [The Exploit Database](https://www.exploit-db.com/), ou encore la [Google Hacking Database](https://www.exploit-db.com/google-hacking-database/).  L'OSCP permet de valider vos compétences concernant la formation PWK (Penetration testing With Kali).
  
Le gros plus de cette formation est qu'elle va vous permettre de pratiquer dans un lab qui simule un réseau d'entreprise. On est donc loin de la classique certif QCM uniquement basée sur du bachotage. Ici vous passerez par toutes les étapes d'un pentest, et on ne vous répètera jamais assez... Enumerate, enumerate, enumerate ! Effectivement la reconnaissance est la première étape primordiale sur laquelle vous devrez mettre l'accent.
  
Mais l'OSCP c'est également une communauté de passionnés, d'entraide, de chans slack ou IRC. Une belle aventure vous attend.  
  
  
**Déroulement**
  
L'OSCP se compose d'un pdf de 375 pages, de ~150 vidéos d'une durée entre 2 ~ 10min, et d'un lab pour vous exercer. A l'issue de ce lab vous pourrez planifier votre examen, ou même avant si vous vous sentez prêt. Le lab est composé de 4 réseaux, un student network, qui lui même route sur un dev network et un it network, ce dernier routant également sur un admin network.  
  
Vous aurez donc à énumerer les machines (services, dns, domain controllers, webapp, vulns, ...), à obtenir un premier accès utilisateur pour ensuite effectuer une élévation des privilèges et devenir root/system. Ne négligez pas la partie post-exploitation.  
    
Vous aurez à pivoter entre les différents réseaux, faire en fonction de solutions antivirales et pare-feux sur les machines. Il y a un nombre équivalent de machines virtuelles WIN/LINUX. Tous les exploits à utiliser sont référencés sur [exploit-db](https://www.exploit-db.com/). Vous pouvez aussi utiliser l'outil en ligne de commande searchsploit.  
  
_Concernant les exploits_:  
Certains exploits fonctionneront out-of-the-box, d'autres demanderont plus d'attention et devront être modifiés pour matcher avec la machine cible, injecter votre propre payload, ...  
  
Un point sur les BO: vous appréhenderez un stack overflow classique sur un exe sans protection DEP ou ASLR (ceci sera pour les autres certifs OSCE, OSEE). Ce fût une section kiff++, ce qui me fait me pencher sérieusement sur l'[OSCE](https://www.offensive-security.com/information-security-certifications/osce-offensive-security-certified-expert/).
  
Si vous souhaitez rallonger la durée du lab, vous pourrez le faire avant l'expiration de ce dernier. Le lab vous préparera au mieux pour l'exam de 24h.  
  
  
**Durée / Tarifs**  
  
![prices]({{ site.url }}/public/images/oscp/prices.png)  
  
Tout dépend du temps que vous pourrez allouer à la formation. Je vous conseillerais, étant donné que vous pouvez étendre la durée du lab (cela vous reviendra un poil plus cher cependant), de ne pas viser une durée trop importante si vous avez une bonne capacité de travail.  
  
Personnellement, je bossais en moyenne 2h par jour en parallèle de mon job et full les week-end. Mais comme on dit quand on aime on ne compte pas. Au final j'étais parti sur un lab de 3 mois, et j'ai pu bouclé la certif en 2 mois. Il me reste donc un mois de lab pour quelques petites douceurs à savoir les dernières machines du réseau Admin :).  
  
  
**Exam / Livrables**
  
Roulements de tambour, vous avez bouclé votre date d'exam, c'est le jour J, vous êtes chaud patate, let's go...  

L'exam se déroule sur 24h. Pendant ces 24h vous aurez à hacker un certain nombre de machines qui vous rapporteront des points en fonction de leur difficulté et du niveau de compromission de la machine (low/high privileged shell).  Un **minimum de 70 points** est requis pour obtenir la certification. Tout ce que vous verrez pendant l'exam a été vu dans le lab (les machines humble/pain/sufferance sont hors scope exam mais faites les).  
Donc mon premier conseil est de passer du temps sur le lab et de compromettre un maximum de machines. 
  
Un exemple, mon exam a commencé à 10h, à 6h le lendemain j'avais réussi à compromettre toutes les machines (5 au total) et recueilli un maximum d'infos pour la rédaction du rapport. J'avais compromis 47 machines pendant le lab.  
  
Vous aurez ensuite à nouveau 24h pour rendre un rapport détaillé et professionnel sur votre test de pénétration. Ce rapport est obligatoire. OffSec vous fournira un template de rapport que vous pourrez utiliser si vous le souhaitez.  
  
__Point bonus__:  
  
Vous pouvez rendre un rapport sur les exercices du PDF et sur les machines compromises du lab. Chaque rapport peut vous rapporter 5 points (un total de 10 points bonus).  
  
  
**Conseils**
  
 - Rédigez les rapports concernant les exercices du pdf et les étapes pour compromettre les machines du lab (10 machines minimum requises). Ces points pourront vous être précieux et vous enlèveront une dose de stress le jour de l'exam. Et puis ne serait-ce que sur un plan pédagogique cela vous permettra d'être certain d'avoir tout assimilé et de ne pas survoler les cours.
 - Organisez votre information et structurez la pour pouvoir y accéder rapidement. Utilisez un soft comme Keepnote/Cherrytree.
 - Utilisez la VM Kali fournie par OffSec.
 - Ne vous précipitez pas, prenez le temps d'avoir une vision précise de votre cible.
 - N'abandonnez-pas, échangez, discutez avec la communauté mais évitez de vous faire spoiler des indices. Vous en tirerez d'autant plus de gratitude en ayant **try harder** :)
 - Le jour de l'exam, faites attention aux 'rabbit-holes'. Si vous explorez une piste trop longtemps passez à autre chose. On ne vous demandera jamais de bruteforcer plus de 30 mins. Et ne négligez aucun détail de votre énumération. **keep calm and enumerate**.
  
![tryharder]({{ site.url }}/public/images/oscp/tryharder.png)  
  
  
**Conclusion**
  
l'OSCP fût une excellente expérience et hautement addictive. Les 24h d'exams sont intenses, mais cela ne sera que du bonheur.  
  
  
N'hésitez pas à me contacter si vous souhaitez des infos sur le sujet!  
[Twitter](https://twitter.com/phackt_ul)  
[Github](https://github.com/phackt)
  
A bientôt!
