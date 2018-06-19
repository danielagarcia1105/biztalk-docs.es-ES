---
title: Agregar el adaptador de Siebel a la consola de administración de BizTalk Server | Documentos de Microsoft
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
ms.openlocfilehash: ebb4a946c9fd987c1a97fa24a9b50d3cdf2f7d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217284"
---
# <a name="add-the-siebel-adapter-to-biztalk-server-administration-console"></a>Agregar el adaptador de Siebel a la consola de administración de BizTalk Server
La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF-Siebel en BizTalk. Si desea utilizar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto personalizado de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Siebel, primero debe agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Este tema proporciona instrucciones sobre cómo agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!IMPORTANT]
>  No es necesario realizar estas tareas si desea configurar un puerto personalizado de WCF para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
## <a name="add-the-siebel-adapter"></a>Agregar el adaptador de Siebel  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.  
  
3.  Haga clic en **adaptadores**, seleccione **New**y haga clic en **adaptador**.  
  
     ![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4.  En el **propiedades del adaptador** diálogo cuadro, especifique un nombre para el adaptador y de la **adaptador** lista, seleccione **WCF-Siebel**.  
  
     ![Agregar WCF &#45; Adaptador de Siebel a BizTalk consola](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)