---
title: Agregar el adaptador de base de datos de Oracle a la consola de administración de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d71e161-addc-47d4-9103-3655f3fb0b0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95ef6f3c4f33ddfdb6dbaca3e1823149ede66abf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997877"
---
# <a name="adding-the-oracle-database-adapter-to-biztalk-server-administration-console"></a>Agregar el adaptador de base de datos de Oracle a la consola de administración de BizTalk Server
Este tema proporciona instrucciones sobre cómo agregar el adaptador de WCF-OracleDB a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!IMPORTANT]
>  No es necesario realizar estas tareas si desea configurar un puerto de WCF-Custom para la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
## <a name="add-the-oracle-database-adapter"></a>Agregar el adaptador de base de datos de Oracle  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Expanda el **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, seleccione **adaptadores**.  
  
3. Haga clic en **adaptadores**, seleccione **New**y seleccione **adaptador**.  
  
    ![Agregar un adaptador](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")  
  
4. En el **propiedades del adaptador** diálogo cuadro, escriba un nombre para el adaptador y desde el **adaptador** lista, seleccione **WCF-OracleDB**.  
  
    ![Adición de WCF&#45;adaptador OracleDB a BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")  
  
5. Seleccione **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)