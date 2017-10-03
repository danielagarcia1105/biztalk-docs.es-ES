---
title: "Aplicaciones de inicio de sesión único tradicionales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a49bdae7-215a-43fb-875e-f64abb37aef0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4396ecfab477fe1ae17b1abbb09ebf71c9bcb58c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="traditional-single-sign-on-applications"></a>Aplicaciones de inicio de sesión único tradicionales
La arquitectura de programación de inicio de sesión único (SSO) contiene un componente de asignación para realizar asignaciones entre aplicaciones y usuarios, un componente de búsqueda para buscar credenciales de un usuario específico, y un componente de administración para llevar a cabo tareas administrativas. Además, SSO también contiene una interfaz de compra de vales de modo que la aplicación pueda emitir y compensar vales.  
  
## <a name="mapping"></a>Asignar  
 Asignar es el proceso de vincular a un usuario especificado con una aplicación determinada. Puede realizar asignaciones entre aplicaciones afiliadas y usuarios que usen `ISSOMapping`, `ISSOMapper`, y `ISSOMapper2`. Con `ISSOMapping`, puede crear, eliminar, habilitar y deshabilitar asignaciones. Con `ISSOMapper` y `ISSOMapper2`, puede obtener y establecer datos de asignaciones para el usuario actual.  
  
## <a name="lookup"></a>Lookup  
 La característica principal de la interfaz de programación de inicio de sesión único (SSO) es la capacidad para buscar credenciales para usuarios específicos. Puede buscar credenciales con `ISSOLookup1` y `ISSOLookup2`. `ISSOLookup1`, permite al usuario recuperar sus propias credenciales externas. En cambio, `ISSOLookup2` también le permite buscar las credenciales de un usuario remoto para una aplicación afiliada local. El primero es necesario para una aplicación de inicio de sesión único (SSO) tradicional, mientras que el segundo es útil cuando se escribe una aplicación de inicio de sesión único (SSO) iniciada por host.  
  
## <a name="administration"></a>Administración  
 Puede realizar muchas de las capacidades administrativas mediante programación a través `ISSOAdmin`, `ISSOAdmin2`, y `ISSOConfigStore`. Estas tareas incluyen la configuración del inicio de sesión único y la creación y descripción de una aplicación para inicio de sesión único. También puede crear y modificar bases de datos SSO mediante `ISSOConfigDB`, `ISSOConfigOM`, y `ISSOConfigSS`. Por último, puede administrar las características de sincronización de contraseña mediante `ISSOPSAdmin`.  
  
## <a name="communication-and-ticketing"></a>Comunicación y compra de vales  
 La aplicación muy probablemente emitirá mensajes para que el usuario pueda comunicarse con una aplicación remota. Para comunicarse con una aplicación remota de manera más segura, deberá emitir y canjear un vale de inicio de sesión único. También es posible emitir y canjear vales mediante programación.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones de inicio de sesión único](../core/single-sign-on-applications.md)