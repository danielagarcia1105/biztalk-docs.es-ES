---
title: Cómo configurar BizTalk Server para enviar mensajes MIME/SMIME de cifrado | Microsoft Docs
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
ms.openlocfilehash: 02f8bb1c1cb11df4d3438f6a8d8af38edf547ea7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981285"
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a>Cómo configurar BizTalk Server para enviar mensajes MIME/SMIME cifrados
Este tema describe cómo configurar BizTalk Server que utilicen certificados para enviar mensajes MIME/SMIME cifrados. El procedimiento siguiente también se aplica a la configuración del envío de mensajes cifrados a través del transporte AS2.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a>Para configurar BizTalk Server para enviar mensajes cifrados  
  
1. Crear una canalización para enviar mensajes cifrados, como sigue:  
  
   > [!NOTE]
   >  Este paso no es necesario al configurar el transporte AS2 para enviar mensajes cifrados, porque el AS2Send y AS2EdiSend canalizaciones que se incluyen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] atender esta función.  
  
   1.  Crear una canalización de envío y, a continuación, arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de la canalización.  
  
   2.  En el **propiedades** ventana, configure la propiedad de cifrado codificador de MIME/SMIME habilitar de componente de canalización para **True**.  
  
       > [!NOTE]  
       >  Puede configurar las propiedades del componente de canalización de envío mediante la consola de administración de servidor BizTalk Server una vez que la canalización se haya implementado en un grupo de BizTalk.  
  
   3.  Genere e implemente la canalización de envío.  
  
2. Configurar el puerto de envío para enviar mensajes cifrados, como sigue:  
  
   1.  Agregue el ensamblado de BizTalk que creó que contiene la canalización de envío a la aplicación de BizTalk, incluidas las ubicaciones de recepción para recibir mensajes cifrados.  
  
       > [!NOTE]  
       >  Este paso no es necesario al configurar el transporte AS2 para enviar mensajes cifrados, ya que las canalizaciones AS2Send y AS2EdiSend están incluidas en la aplicación EDI de BizTalk.  
  
   2.  Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior.  
  
   3.  Asignar el certificado de cifrado que ha instalado haciendo clic con el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificado**. Haga clic en **examinar**, busque el certificado que desea asignar a este puerto de envío y, a continuación, haga clic en **Aceptar**.  
  
       > [!NOTE]  
       >  Si el certificado no existe en el equipo local, en el **huella digital** , escriba o pegue la huella digital del certificado y, a continuación, haga clic en **Aceptar**. La huella digital de certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal.