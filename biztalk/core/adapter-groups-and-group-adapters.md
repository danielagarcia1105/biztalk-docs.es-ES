---
title: Grupos de adaptadores y adaptadores de grupo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e0a9423-99dd-4474-afa1-fd8e1d074cd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcf10f50857026893245cc567783b649f614c4f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225380"
---
# <a name="adapter-groups-and-group-adapters"></a>Grupos de adaptadores y adaptadores de grupo
Un *grupo de adaptadores* es un mecanismo de administración que puede usar para recopilar y organizar un conjunto de adaptadores. En cambio, un *adaptador de grupo* es un componente que da servicio a todos los adaptadores de un grupo de adaptadores. Por ejemplo, puede escribir un conjunto de adaptadores y que utilicen todos el mismo componente COM para transmitir sincronizaciones de contraseñas sobre TCP/IP. El conjunto de adaptadores se llama grupo de adaptadores, mientras que el componente que da servicio a todos ellos se llama adaptador de grupo. Los grupos de adaptadores se describen en el almacén de configuración. Puede recuperar la información y las actualizaciones en un grupo de adaptadores mediante `ISSOPSAdapter.ReceiveNotification`.  
  
 Un adaptador de grupo tiene el mismo nombre que el grupo de adaptadores. Aparte de la restricción en el nombre, un adaptador de grupo es idéntico a un adaptador normal. Por ejemplo, un adaptador de grupo puede tener grupos de acceso y propiedades de configuración independientes, como se describe en su archivo de configuración. Un adaptador de grupo está con toda probabilidad en el mismo equipo que los adaptadores del grupo de adaptadores. No obstante, esto no es obligatorio. Del mismo modo, cabe esperar que todos los adaptadores del mismo grupo de adaptadores estén en el mismo equipo.  
  
 Mediante el uso de `ISSOPSAdapter.InitializeAdapter`, se puede tener acceso e inicializar un adaptador de grupo durante el inicio. Cuando inicializa un adaptador de grupo, el sistema informa al adaptador de grupo de todos los adaptadores del grupo de adaptadores que hay en el sistema en uso. Además, el sistema envía notificaciones al adaptador de grupo cada vez que se agrega, elimina, habilita o deshabilita un adaptador en el grupo de adaptadores. Sin embargo, el adaptador de grupo no recibe ninguna notificación de cambio de contraseña.  
  
 Los grupos de adaptadores y los adaptadores de grupo son opcionales al utilizar la herramienta de administración.  
  
## <a name="see-also"></a>Vea también  
 [Adaptadores de sincronización de contraseña](../core/password-sync-adapters.md)