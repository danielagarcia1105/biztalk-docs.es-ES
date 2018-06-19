---
title: Cómo configurar el servidor BizTalk Server para enviar mensajes MIME/SMIME de cifrado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f67152-5f80-4040-a9d6-0819fab7fcb5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83b5f28ac3716376aa93cff22f933363825615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297612"
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a>Cómo configurar BizTalk Server para enviar mensajes cifrados de MIME/SMIME
En este tema se describe cómo configurar BizTalk Server que utilicen certificados para enviar mensajes cifrados de MIME/SMIME. El procedimiento siguiente también se aplica a la configuración de enviar mensajes cifrados a través de transporte AS2.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a>Para configurar BizTalk Server para enviar mensajes cifrados  
  
1.  Crear una canalización para enviar mensajes cifrados, como se indica a continuación:  
  
    > [!NOTE]  
    >  Este paso no es necesario al configurar el transporte de AS2 para enviar mensajes cifrados, ya que la AS2Send y AS2EdiSend canalizaciones que se incluyen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servir esta función.  
  
    1.  Crear una canalización de envío y, a continuación, arrastre el componente de canalización de codificador de MIME/SMIME en la fase de codificación de la canalización.  
  
    2.  En el **propiedades** ventana, configure la propiedad de cifrado codificador de MIME/SMIME habilitar de componente de canalización para **True**.  
  
        > [!NOTE]  
        >  Puede configurar las propiedades del componente de canalización de envío mediante la consola de administración de servidor BizTalk Server una vez que la canalización se haya implementado en un grupo de BizTalk.  
  
    3.  Genere e implemente la canalización de envío.  
  
2.  Configurar el puerto de envío para enviar mensajes cifrados, como se indica a continuación:  
  
    1.  Agregue el ensamblado de BizTalk que ha creado que contiene la canalización de envío a la aplicación de BizTalk incluidas las ubicaciones de recepción para recibir mensajes cifrados.  
  
        > [!NOTE]  
        >  Este paso no es necesario al configurar el transporte de AS2 para enviar mensajes cifrados, puesto que las canalizaciones AS2Send y AS2EdiSend se incluyen en la aplicación EDI de BizTalk.  
  
    2.  Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior.  
  
    3.  Asigne el certificado de cifrado que instaló haciendo clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificado**. Haga clic en **examinar**, busque el certificado que desea asignar a este puerto de envío y, a continuación, haga clic en **Aceptar**.  
  
        > [!NOTE]  
        >  Si el certificado no existe en el equipo local, en la **huella digital** , escriba o pegue la huella digital del certificado y, a continuación, haga clic en **Aceptar**. La huella digital de certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal.