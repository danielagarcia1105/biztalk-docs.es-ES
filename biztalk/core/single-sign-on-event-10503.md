---
title: 'Inicio de sesión único: Evento 10503 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53c02388304fa9fab0b518517ba51b2db94412f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271116"
---
# <a name="single-sign-on-event-10503"></a>Inicio de sesión único: Evento 10503
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10503|  
|Origen del evento|ENTSSO|  
|Componente|N\D|  
|Nombre simbólico|SSO_ERROR_SERVICE_START_FAILED|  
|Texto del mensaje|Error al iniciar el servicio SSO.%r<br /><br /> Código de error: %1|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error indica que el servicio ENTSSO no pudo iniciarse debido a una excepción.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  
  
-   Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.  
  
 Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Uso de SSO](../core/using-sso.md)