---

copyright:
  years: 2014, 2018
lastupdated: "2018-02-23"

keywords: SSH keys, IBM Cloud infrastructure customer, public SSH key

subcollection: ssh-keys

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Aggiunta di una chiave SSH
{: #adding-an-ssh-key}

Puoi aggiungere le chiavi SSH al tuo account se sei un utente autorizzato. Ogni account può avere fino a 100 chiavi SSH in qualsiasi momento. In {{site.data.keyword.slportal_full}}, le chiavi SSH sono spesso utilizzate nel [processo di ricaricamento SO](/docs/infrastructure/software?topic=software-reloading-the-os) e possono inoltre essere utilizzate quando esegui il provisioning di un nuovo dispositivo.

**Nota:** [Genera la chiave SSH pubblica ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://help.github.com/articles/generating-ssh-keys){: new_window} con il dispositivo per cui stai aggiungendo una chiave prima di aggiungere una chiave SSH al tuo account.

Segui queste istruzioni per aggiungere una chiave SSH al tuo account.
1. Accedi alla schermata **SSH Keys**. Fai riferimento a [Introduzione alla chiavi SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-getting-started-tutorial).
2. Fai clic su **Add**.
3. Fai clic su **Browse** per trovare il file della chiave pubblica o immettilo manualmente nella casella di testo **Key Contents**.
4. Immetti un **nome breve** per la chiave SSH nel campo **Label**.
5. Immetti tutte le note applicabili nel campo **Notes**, se necessario.
6. Fai clic su **Add** per aggiungere la chiave SSH. Fai clic su **Cancel** per annullare l'azione.

## Passi successivi

Dopo aver aggiunto la chiave SSH, questa viene visualizzata nell'elenco delle chiavi SSH.
Puoi [modificare i dettagli della chiave](/docs/infrastructure/ssh-keys?topic=ssh-keys-editing-details-for-an-ssh-key) in qualsiasi momento. Puoi anche [rimuovere la chiave SSH](/docs/infrastructure/ssh-keys?topic=ssh-keys-removing-an-ssh-key) dall'elenco. Rimuovi le chiavi SSH obsolete il prima possibile per garantire che lo spazio sia sufficiente se hai bisogno di aggiungere ulteriori chiavi.
