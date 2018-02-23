---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-12"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Incluindo uma chave SSH

É possível incluir chaves SSH na sua conta se você é um usuário autorizado. Cada conta pode ter até 100
chaves SSH a qualquer momento. No {{site.data.keyword.slportal_full}}, as chaves SSH são usadas com mais frequência no [Processo de recarregamento de OS](../software/vsi_reload_os.html){:new_window} e também podem ser usadas ao fornecer um novo dispositivo. 

**Nota:** [gere a chave SSH pública ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://help.github.com/articles/generating-ssh-keys){: new_window} com o dispositivo para o qual você está incluindo uma chave antes de incluir uma chave SSH na sua conta. 

Siga estas etapas para incluir uma chave SSH na sua conta.
1. Acesse a tela **Chaves SSH**. Consulte [Introdução às Chaves SSH](index.html).
2. Clique na guia **Incluir** na parte superior da tela.
3. Clique em **Procurar** para localizar o arquivo de chave pública ou insira-o manualmente na caixa de texto **Conteúdo de chave**.
4. Insira um **nome abreviado** para a Chave SSH no campo **Rótulo**.
5. Insira quaisquer notas aplicáveis no campo **Notas**, se necessário.
6. Clique em **Incluir** para incluir a chave SSH. Clique em **Cancelar** para cancelar a ação.

## Próximas Etapas

Depois de incluir a chave SSH, ela aparece na lista de chaves SSH.
É possível [editar os detalhes da chave](edit-details-ssh-key.html) a qualquer momento. Também é possível [remover a chave SSH](remove-ssh-key.html){:new_window} da lista. Remova as chaves SSH obsoletas assim que possível para assegurar que espaço esteja disponível caso você precise incluir
mais chaves.