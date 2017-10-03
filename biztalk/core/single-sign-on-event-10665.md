---
title: "Inicio de sesión único: Evento 10665 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a7d4d5c4140448914ff77b09a692cc3a2136dfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10665"></a>Inicio de sesión único: Evento 10665
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10665|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_WARN_NO_PROPERTIES|  
|Texto del mensaje|Error al leer las propiedades del adaptador de sincronización de contraseñas. Se usan los valores predeterminados.%r<br /><br /> Adaptador: %1 %r<br /><br /> Código de error: %2|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que se produjo un error al leer las propiedades predeterminadas del adaptador de sincronización de contraseñas. Cada adaptador de sincronización de contraseñas tiene propiedades de configuración asociadas a él. Estas propiedades se guardan en el almacén de configuración de SSO y se crean mediante las herramientas de línea de comandos o la MMC de administración de SSO cuando se crea el adaptador de sincronización de contraseñas.  Si dicho adaptador se creó a través de otro medio, es posible que falten propiedades y, por lo tanto, puede emitirse este error.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Compruebe las propiedades del adaptador de sincronización de contraseñas.  
  
-   Vuelva a crear el adaptador de sincronización de contraseñas.  
  
## <a name="more-info"></a>Más información
  
-   **Propiedades del adaptador de sincronización de contraseñas: Opciones**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [Sincronización de contraseña](../core/password-synchronization2.md)