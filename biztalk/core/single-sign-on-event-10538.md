---
title: 'Inicio de sesión único: Evento 10538 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac7e027c240091e6a1a67ff53a41a00afeef7288
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270188"
---
# <a name="single-sign-on-event-10538"></a>Inicio de sesión único: Evento 10538
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10538|  
|Origen del evento|ENTSSO|  
|Componente|CO|  
|Nombre simbólico|SSO_WARN_APP_DISABLED|  
|Texto del mensaje|Actualmente la aplicación está deshabilitada.%r<br /><br /> Nombre de la aplicación: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que el administrador de aplicaciones deshabilitó la aplicación afiliada de SSO.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar la advertencia, realice una o varias de las acciones siguientes:  
  
-   Póngase en contacto con el administrador de aplicaciones para habilitar la aplicación afiliada de SSO. Esto puede realizarse mediante las herramientas de administración de SSO (GUI o línea de comandos).  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md)  
  
-   [Cómo deshabilitar una aplicación afiliada](../core/how-to-disable-an-affiliate-application.md)