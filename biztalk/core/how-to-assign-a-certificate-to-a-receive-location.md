---
title: Cómo asignar un certificado a una ubicación de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 54ae300e-62c5-480f-a9b7-e5c3457a0f80
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094b49aba2e55e20ad32304f5b700126a2322d75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995317"
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a>Cómo asignar un certificado a una ubicación de recepción
En este tema se describe cómo usar la consola de administración de BizTalk Server para asignar un certificado de seguridad a una ubicación de recepción. Este procedimiento sólo debe realizarse en una ubicación de recepción bidireccional. El certificado debe existir en el almacén de certificados Otras personas del equipo en el que se ejecuta BizTalk Server o, de lo contrario, no se procesarán los mensajes asociados con esta ubicación de recepción y se registrarán errores.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a>Para asignar un certificado a una ubicación de recepción  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desee asignar un certificado a una ubicación de recepción.  
  
3. Expanda **ubicaciones de recepción**, haga clic en la ubicación de recepción, haga clic en **propiedades**y, a continuación, haga clic en **certificado**.  
  
4. Si el certificado existe en el equipo local, haga clic en **examinar**, busque el certificado que desea asignar a esta ubicación de recepción y, a continuación, haga clic en **Aceptar**. De lo contrario, omita este paso.  
  
   > [!NOTE]
   >  Si realiza esta operación desde un equipo remoto, asegúrese de que exista el certificado en el equipo en que se ejecute BizTalk Server y no sólo en el equipo local. En caso contrario, la ubicación de recepción no podrá procesar los mensajes.  
  
5. Si el certificado no existe en el equipo local, en el **huella digital** , escriba o pegue la huella digital del certificado y, a continuación, haga clic en **Aceptar**. La huella digital de certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal.  
  
## <a name="see-also"></a>Vea también  
 [Administración de ubicaciones de recepción](../core/managing-receive-locations.md)