---
title: Agregar el adaptador de SQL a la consola de administración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff3eb1aa8870316ec506a61658c34db6acc7f62c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005733"
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a>Agregar el adaptador de SQL a la consola de administración de BizTalk Server
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede usarse como un puerto de WCF-Custom o WCF-SQL en BizTalk. Si desea usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a través de un puerto de WCF-Custom, es necesario agregar el puerto de WCF-Custom para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada. Sin embargo, si desea usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a través de un puerto de WCF-SQL, primero debe agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Este tema muestra cómo agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!IMPORTANT]
>  No es necesario seguir estos pasos si desea configurar un puerto de WCF-Custom para la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="add-the-sql-adapter"></a>Agregar el adaptador de SQL  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, seleccione **adaptadores**.  
  
3. Haga clic en **adaptadores**, apunte a **New**y seleccione **adaptador**.  
  
    ![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. En el **propiedades del adaptador** diálogo cuadro, escriba un nombre para el adaptador y de la **adaptador** lista, seleccione **WCF-SQL**.  
  
    ![Agregar WCF&#45;adaptador SQL a BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")  
  
5. Seleccione **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)