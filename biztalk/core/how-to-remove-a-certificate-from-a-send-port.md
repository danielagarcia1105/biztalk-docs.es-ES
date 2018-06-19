---
title: Cómo quitar un certificado de un puerto de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5193b1b6003660aac0e0b427da0f0a338b56d8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254508"
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a>Cómo quitar un certificado de un puerto de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para quitar un certificado de seguridad de un puerto de envío. Al hacerlo, el puerto de envío dejará de cifrar mensajes; los mensajes se enviarán en texto no cifrado. Cuando se quita un certificado de un puerto de envío, no se quita del almacén de certificados.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede quitar un certificado de seguridad de un puerto de envío durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a>Para quitar un certificado de un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee quitar un certificado de un puerto de envío.  
  
3.  Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificados**.  
  
4.  Haga clic en **quitar certificado**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)