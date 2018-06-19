---
title: Archivo de configuración XML para el adaptador de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, mqsconfigwiz
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], mqsconfigwiz
- mqsconfigwiz [MQSeries adapters]
ms.assetid: 5f19e55c-0f2c-46d7-bb5d-1eb147c296b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0356c69b90f0dcfd5fc636b302a97b2de5674b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289772"
---
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a>Archivo de configuración XML para el adaptador de MQSeries
Leer el archivo de configuración XML **mqsconfigwiz** contiene la misma información que un usuario especifica al usar la versión de Windows del asistente. Esta información incluye la identidad de aplicación, el Id. de usuario y la contraseña si es necesario, el nombre de función y una lista de usuarios que forman parte de la función.  
  
 A continuación se ofrece un ejemplo de este tipo de archivo:  
  
```  
<MQSeriesConfig>  
    <AppIdentity>thisuser</AppIdentity>  
    <userid>domain\username</userid>  
    <password>Bippity.Boppity</password>  
    <rolename>CreatorOwner</rolename>  
    <userlist>  
        <username>domain\user1</username>  
        <username>domain\user2</username>  
    </userlist>  
</MQSeriesConfig>  
```  
  
 Puede usar **thisuser**, **InteractiveUser**, **LocalService**, o **NetworkService** como valores para **AppIdentity** . Use la **userid** y **contraseña** elementos sólo con **thisuser**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración silenciosa del adaptador de MQSeries](../core/silent-configuration-of-the-mqseries-adapter.md)