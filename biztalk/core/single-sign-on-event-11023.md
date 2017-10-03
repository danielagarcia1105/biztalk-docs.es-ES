---
title: "Inicio de sesión único: Evento 11023 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd65ac5cab5b49f43e0c3649cf205f7f6dc2ceaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11023"></a>Inicio de sesión único: Evento 11023
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11023|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_WARN_WINDOWS_PASSWORD_DELETED|  
|Texto del mensaje|Se eliminó una contraseña de Windows no válida en la base de datos de SSO para evitar el bloqueo de cuenta.%r<br /><br /> Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows.%r<br /><br /> Id. de seguimiento: %1 %r<br /><br /> Adaptador: %2 %r<br /><br /> Cuenta de Windows: %3|  
  
## <a name="explanation"></a>Explicación  
 Se eliminó una contraseña de Windows no válida.  
  
## <a name="user-action"></a>Acción del usuario  
 Use las herramientas de administración de SSO para establecer las credenciales externas para esta cuenta de Windows. Para obtener más información, consulte [mediante SSO](../core/using-sso.md).