---
title: Agregar el adaptador de Siebel a la consola de administración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b64d0bdc-ac83-46c9-b27d-625088a013d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f8c30567849a0342432cb53e0c2de7959c175c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967429"
---
# <a name="add-the-siebel-adapter-to-biztalk-server-administration-console"></a>Agregar el adaptador de Siebel a la consola de administración de BizTalk Server
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF-Siebel en BizTalk. Si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Custom, es necesario agregar el puerto de WCF-Custom para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Siebel, primero debe agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Este tema proporciona instrucciones sobre cómo agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!IMPORTANT]
>  No es necesario realizar estas tareas si desea configurar un puerto de WCF-Custom para la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
## <a name="add-the-siebel-adapter"></a>Agregar el adaptador de Siebel  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.  
  
3. Haga clic en **adaptadores**, apunte a **New**y haga clic en **adaptador**.  
  
    ![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. En el **propiedades del adaptador** diálogo cuadro, especifique un nombre para el adaptador y desde el **adaptador** lista, seleccione **WCF-Siebel**.  
  
    ![Agregar WCF&#45;adaptador de Siebel a BizTalk consola](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")  
  
5. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)