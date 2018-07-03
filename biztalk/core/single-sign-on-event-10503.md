---
title: 'De sesión único: Evento 10503 | Microsoft Docs'
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
ms.openlocfilehash: b90af01551359b5caa1a5404facc9e3fece95673
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990717"
---
# <a name="single-sign-on-event-10503"></a>De sesión único: Evento 10503
## <a name="details"></a>Detalles  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  Nombre del producto   |                   Inicio de sesión único (SSO) empresarial                   |
| Versión del producto |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    Identificador del evento     |                             10503                             |
|  Origen del evento   |                            ENTSSO                             |
|    Componente    |                              N\D                              |
|  Nombre simbólico  |                SSO_ERROR_SERVICE_START_FAILED                 |
|  Texto del mensaje   | Error al iniciar el servicio SSO.%r<br /><br /> Código de error: %1 |

## <a name="explanation"></a>Explicación  
 Este evento de error indica que el servicio ENTSSO no pudo iniciarse debido a una excepción.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente:  

- Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Uso de SSO](../core/using-sso.md)
