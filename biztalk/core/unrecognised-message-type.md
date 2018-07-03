---
title: No se ha reconocido el tipo de mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14a76219470f971d2c83e11dabfec7fa912dcb5f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992869"
---
# <a name="unrecognised-message-type"></a>Tipo de mensaje no reconocido
## <a name="details"></a>Detalles  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                UnRecognizedMessageType                                 |
|  Texto del mensaje   |                   Tipo de mensaje no reconocido. No se puede continuar.                   |

## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque no se ha implementado ningún esquema de documento para el tipo de documento de un conjunto de transacciones en dicho intercambio o bien BizTalk Server no puede determinar el tipo de documento a partir del código de identificador, la versión y el espacio de nombres del conjunto de transacciones.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  

- Implemente un esquema de documento para el tipo de documento de un conjunto de transacciones en el intercambio y vuelva a enviar el intercambio.  

- Compruebe que los siguientes valores definen un esquema válido: de X12, escriba el espacio de nombres de destino, la versión y el documento; para EDIFACT, el espacio de nombres de destino, número de versión de mensaje, el número de versión de mensaje y tipo de mensaje. Para obtener más información, consulte la sección "Detección de esquemas" del tema "Resolución de entidades, detección de esquemas y autorización para los mensajes EDI recibidos" de la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].
