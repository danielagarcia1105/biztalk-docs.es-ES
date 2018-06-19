---
title: Cómo asignar un certificado a un puerto de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, assigning
- managing [send ports], certificates
- assigning certificates
- certificates, send ports
ms.assetid: ba9e9c8b-f5b6-4fee-9e89-31b0f1df6ed4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec19c845c6b0cfb5d19bd7a961fe9ddfbcf2a3d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247484"
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a>Cómo asignar un certificado a un puerto de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para asignar un certificado de seguridad a un puerto de envío. El certificado debe existir en el almacén de certificados Otras personas del equipo en el que se ejecuta BizTalk Server o, de lo contrario, no se procesarán los mensajes asociados con este puerto de envío y se registrarán errores.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede asignar un certificado de seguridad a un puerto de envío durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a>Para asignar un certificado a un puerto de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea asignar un certificado a un puerto de envío.  
  
3.  Expanda **puertos de envío**, haga clic en el puerto de envío, haga clic en **propiedades**y, a continuación, haga clic en **certificado**.  
  
4.  Si el certificado existe en el equipo local, haga clic en **examinar**, busque el certificado que desea asignar a este puerto de envío y, a continuación, haga clic en **Aceptar**. De lo contrario, omita este paso.  
  
    > [!NOTE]
    >  Aun si el certificado existe en el equipo local, también debe existir en el equipo en el que se ejecute BizTalk Server (si no es el mismo que el primero) antes de que el puerto de envío pueda procesar mensajes.  
  
5.  Si el certificado no existe en el equipo local, en la **huella digital** , escriba o pegue la huella digital del certificado y, a continuación, haga clic en **Aceptar**. La huella digital de certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal.  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar puertos de envío](../core/creating-and-configuring-send-ports.md)