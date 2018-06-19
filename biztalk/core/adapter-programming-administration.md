---
title: Administración de programación del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38563b3c-6d52-4e4e-ac6e-74f46ce22c6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b19e3285357bb067614aae9472eb099470fe27f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229812"
---
# <a name="adapter-programming-administration"></a>Administración de programación del adaptador
Un adaptador es un tipo especial de aplicación de almacenamiento de configuración: es decir, un adaptador es un componente que comparte un espacio de nombres con otros Single Sign-On y aplicaciones de almacén de configuración. Por lo tanto, puede tener acceso a información sobre un adaptador mediante ISSOConfigStore. Sin embargo, a diferencia de la aplicación de almacenamiento de configuración, con la interfaz ISSOAdmin no realiza funciones administrativas en un adaptador. En lugar de ello, administra un adaptador mediante ISSOPSAdmin. La razón de una interfaz de administración de un adaptador especializado es que el sistema pueda coordinar otras actividades con el almacenamiento de configuración.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de programación del adaptador](../core/adapter-programming-configuration.md)   
 [Grupos de adaptadores y adaptadores de grupo](../core/adapter-groups-and-group-adapters.md)   
 [Adaptadores de sincronización de contraseña](../core/password-sync-adapters.md)