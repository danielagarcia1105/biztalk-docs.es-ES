---
title: Agregar el adaptador de Oracle E-Business Suite a la consola de administración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b126aa-2a05-49fa-80e1-f1d5c21ad60f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77d7bbc13857f51a9bc4072c2f8a02407a5da2ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977261"
---
# <a name="add-the-oracle-e-business-suite-adapter-to-biztalk-server-administration-console"></a>Agregar el adaptador de Oracle E-Business Suite a la consola de administración de BizTalk Server
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] puede usarse como un puerto de WCF-Custom o WCF-OracleEBS en BizTalk Server. Si desea usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a través de un puerto de WCF-Custom, es necesario agregar el puerto de WCF-Custom para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a través de un puerto de WCF-OracleEBS, primero debe agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Este tema proporciona instrucciones sobre cómo agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!IMPORTANT]
>  Si desea configurar un puerto de WCF-Custom para la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], no es necesario realizar este procedimiento.  
  
### <a name="to-add-the-oracle-e-business-suite-adapter"></a>Para agregar el adaptador para Oracle E-Business Suite  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola, expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **adaptadores**.  
  
3. Haga clic en **adaptadores**, apunte a **New**y haga clic en **adaptador**.  
  
    ![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. En el **propiedades del adaptador** diálogo cuadro, especifique un nombre para el adaptador y desde el **adaptador** lista, seleccione **WCF-OracleEBS**.  
  
    ![Agregar WCF&#45;adaptador OracleEBS a BizTalk](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")  
  
5. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)