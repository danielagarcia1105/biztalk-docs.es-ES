---
title: Se produjo un error de autenticación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36524da9-da91-41e7-bf73-7781cde20c80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180645d30c5cccc64eacd57730539bbca220f32f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278692"
---
# <a name="there-was-an-authentication-failure"></a>Error de autenticación
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|DescPartyNotFound|  
|Texto del mensaje|Se produjo un error de autenticación. Asegúrese de que existe una entidad que coincida con el mensaje que se está procesando, y que la información de seguridad y contraseña del mensaje coincide con la configuración de la entidad.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque BizTalk Server no pudo autenticar al remitente del mensaje.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Compruebe que el calificador e identificador del remitente que aparece en el encabezado del intercambio (campos ISA5 e ISA6 para X12 o UNB2.1 y UNB2.2 para EDIFACT) coincide con el calificador e identificador del remitente que aparece en las propiedades de una entidad (tal como se define en la página Propiedades de procesamiento de intercambio del cuadro de diálogo Propiedades de EDI).  
  
-   Compruebe que la información de seguridad y de contraseña que aparece en el encabezado del intercambio (campos IISA3 e ISA4 para X12 o UNB6.1 y UNB6.2 para EDIFACT) coincide con la información de seguridad y de contraseña que aparece en las propiedades de una entidad (tal como se define en la página Propiedades de procesamiento de intercambio del cuadro de diálogo Propiedades de EDI).