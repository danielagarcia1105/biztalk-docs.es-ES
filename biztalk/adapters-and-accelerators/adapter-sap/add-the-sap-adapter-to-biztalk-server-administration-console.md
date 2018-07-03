---
title: Agregar el adaptador SAP a la consola de administración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95fc925d-0aac-4f0d-a19d-ad27469e4b3c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a8913e982a94a2b850bae1aab668f9672e86fe8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986629"
---
# <a name="add-the-sap-adapter-to-biztalk-server-administration-console"></a>Agregar el adaptador SAP a la consola de administración de BizTalk Server
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF SAP en BizTalk. Si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de WCF-Custom, es necesario agregar el puerto de WCF-Custom para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de un puerto de SAP de WCF, primero debe agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Este tema proporciona instrucciones sobre cómo agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!IMPORTANT]
>  No es necesario realizar estas tareas si desea configurar un puerto de WCF-Custom para la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="add-the-sap-adapter"></a>Agregar el adaptador SAP  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.  
  
3. Haga clic en **adaptadores**, apunte a **New**y haga clic en **adaptador**.  
  
    ![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. En el **propiedades del adaptador** diálogo cuadro, especifique un nombre para el adaptador y desde el **adaptador** lista, seleccione **SAP de WCF**.  
  
    ![Agregar adaptador SAP a BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")  
  
5. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)