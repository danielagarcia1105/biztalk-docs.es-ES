---
title: Cómo configurar BizTalk Server para enviar firmados MIME o mensajes SMIME | Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba42463b-2c12-4329-919e-aca427d14eee
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e1f3e01179f26c825480bb3a7de8d13b8539129
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005469"
---
# <a name="how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages"></a>Cómo configurar BizTalk Server envíe firmados MIME o mensajes SMIME
En este tema se describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utilizar certificados para enviar mensajes MIME/SMIME firmados. El procedimiento siguiente también se aplica a la configuración del envío de mensajes firmados mediante transporte AS2.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe ser iniciado sesión como miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores.  
  
### <a name="to-configure-biztalk-server-to-send-signed-messages"></a>Para configurar BizTalk Server para enviar mensajes firmados  
  
1. Crear una canalización para enviar mensajes firmados, como sigue:  
  
   > [!NOTE]
   >  Este paso no es necesario al configurar el transporte AS2 para enviar mensajes firmados, porque el AS2Send y AS2EdiSend canalizaciones que se incluyen en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] atender esta función.  
  
   1. Crear una canalización de envío y, a continuación, arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de la canalización.  
  
   2. En el **propiedades** ventana, configure la propiedad de tipo de firma de codificador de MIME/SMIME canalización componente ClearSign o BlobSign.  
  
      > [!NOTE]
      >  Si también usa cifrado, solo se puede seleccionar BlobSign.  
      > 
      > [!NOTE]
      >  Puede configurar las propiedades del componente de canalización de envío mediante la Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], una vez que la canalización se haya implementado en un grupo de BizTalk.  
      > 
      > [!NOTE]
      >  El componente de canalización de codificador de MIME/SMIME realiza tanto el cifrado como la firma digital (cuando se configura para que realice las dos funciones). Por lo tanto, si configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes cifrados y firmados, puede usar la misma canalización de envío. Es decir, no es necesario crear canalizaciones diferentes para el cifrado y la firma digital.  
  
   3. Genere e implemente la canalización de envío.  
  
2. Configurar el puerto de envío para enviar mensajes firmados, como sigue:  
  
   1. Agregue el ensamblado de BizTalk que creó que contiene la canalización de envío a la aplicación de BizTalk que incluye los puertos de envío para enviar mensajes firmados.  
  
      > [!NOTE]
      >  Este paso no es necesario al configurar el transporte AS2 para enviar mensajes firmados puesto que las canalizaciones AS2Send y AS2EdiSend se incluyen en la aplicación EDI de BizTalk en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
   2. Configure el puerto de envío en la aplicación de BizTalk con la canalización de envío que creó en el procedimiento anterior.  
  
3. Configure el grupo con un certificado para enviar mensajes firmados, como sigue:  
  
   1. Configurar el grupo de BizTalk con el certificado de firma que instaló expandiendo el grupo de BizTalk en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, hacer clic **grupo de BizTalk**y, a continuación, haga clic en  **Propiedades**.  
  
   2. Haga clic en la ficha certificado, haga clic en **examinar**, seleccione el certificado adecuado y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Configurar certificados para MIME o mensajes SMIME](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)