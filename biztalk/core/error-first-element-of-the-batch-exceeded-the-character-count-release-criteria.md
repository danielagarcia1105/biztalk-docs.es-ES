---
title: El primer elemento del lote excedía el recuento de caracteres versión criterio establecido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b06f8f-247d-4e93-8c4e-5e86e4ad70c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 880e29ceb2be1c574aeaec248ce47317e332e5a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972661"
---
# <a name="the-first-element-of-the-batch-exceeded-the-character-count-release-criteria-set"></a>El primer elemento del lote excedía el recuento de caracteres, el criterio de publicación establecido
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                         |
| Versión del producto |                                                                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                                     |
|    Identificador del evento     |                                                                                                                                 -                                                                                                                                  |
|  Origen del evento   |                                                                                       EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                       |
|    Componente    |                                                                                                                          Motor de procesamiento por lotes                                                                                                                           |
|  Nombre simbólico  |                                                                                                                   FirstElementExceededCharCount                                                                                                                    |
|  Texto del mensaje   | El primer elemento del lote excedía el recuento de caracteres, el criterio de publicación establecido. Modifique los criterios de lanzamiento de recuento de caracteres para poder procesar el mensaje. Una vez modificada la configuración, el mensaje debe enviarse de nuevo al sistema de procesamiento por lotes |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la orquestación por lotes no pudo generar el intercambio por lotes porque el número de caracteres del primer elemento de lote seleccionado por la orquestación de lote superó el número de caracteres especificado por la propiedad "Número máximo de caracteres de un intercambio" de los criterios de lanzamiento de lote. Tenga en cuenta que el número de caracteres comparado con el máximo no incluye el número de caracteres del sobre.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
1.  Aumente la propiedad "Número máximo de caracteres de un intercambio" de la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI para la entidad como receptor de intercambio. Para ello, debe detener la instancia de orquestación, aumentar el número máximo de caracteres en la propiedad y, a continuación, reiniciar la instancia de orquestación. Pida al remitente que vuelva a enviar el mensaje.  
  
2.  Pida al remitente que envíe conjuntos de transacciones con menos caracteres que el número máximo de caracteres.