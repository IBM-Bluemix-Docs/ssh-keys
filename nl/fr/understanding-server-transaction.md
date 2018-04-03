---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Compréhension d'une transaction serveur

Lorsqu'un serveur {{site.data.keyword.Bluemix_short}} est mis à disposition, un système d'exploitation est chargé ou un logiciel est installé, il est placé dans une *transaction*.  Une transaction est une série d'étapes automatisée que les systèmes de gestion {{site.data.keyword.Bluemix_notm}} exécutent pour configurer des serveurs de client. 

Si l'un de vos serveurs figure dans une transaction, un lien apparaît dans les notes de serveur dans les listes de matériel. Vous pouvez cliquer sur ce lien pour voir les transactions en attente pour ce serveur spécifique. Un tableau présentant les données relatives à la transaction actuellement en cours s'affichera. 

* La zone **ID** correspond à l'ID interne d'une transaction. Si vous soumettez un ticket au sujet d'une transaction, ajoutez ce numéro. 
* La zone **Groupe** contient une brève description du type de transaction. Par exemple, *Rechargement de système d'exploitation MS* signifie qu'un système d'exploitation Microsoft est en train d'être rechargé sur la machine. 
* La zone **Statut en cours** correspond au nom de l'étape de transaction en cours. Par exemple, *INSTALL_SE* est l'étape de transaction pour *Rechargement de système d'exploitation MS*, et signifie que Windows est actuellement en cours d'installation sur la machine. 
* Les zones **Temps écoulé et Temps moyen** fonctionnent ensemble. La zone Temps écoulé indique depuis combien de temps l'étape de transaction en cours s'exécute. La zone Temps moyen indique la durée moyenne d'exécution de cette étape. Si le temps écoulé est beaucoup plus long que le temps moyen, vous devrez peut-être soumettre un ticket au support afin de demander le statut de l'opération. 
