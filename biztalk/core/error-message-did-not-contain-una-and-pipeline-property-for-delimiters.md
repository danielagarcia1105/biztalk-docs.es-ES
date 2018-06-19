---
title: Mensaje no contenía UNA y propiedad de canalización para delimitadores tenía el formato correcto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761d820-e09d-4949-bb41-da9e66054c60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6310c96f897126a498772f2147a20c84f7e926a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241844"
---
# <a name="message-did-not-contain-una-and-pipeline-property-for-delimiters-was-incorrect-format"></a>El mensaje no contenía UNA, y la propiedad de canalización para delimitadores no tenía el formato correcto
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|EfactDelimiterIncorrectFormat|  
|Texto del mensaje|El mensaje no contenía UNA, y la propiedad de canalización para delimitadores no tenía el formato correcto '{0}'.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio EDIFACT entrante porque no pudo determinar los separadores requeridos para procesar el intercambio. Esto puede suceder si el intercambio no tiene un segmento UNA y la propiedad de la canalización EfactDelimiters no define de forma adecuada los separadores.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
1.  Asegúrese de que el intercambio tenga un segmento UNA que defina los separadores para el intercambio y vuelva a enviar el intercambio.  
  
2.  Configure la propiedad de la canalización EfactDelimiters para la canalización de envío. Para ello, abra la consola de administración de BizTalk Server, haga clic con el botón secundario en la ubicación de recepción que va a recibir el intercambio, haga clic en Propiedades y en los puntos suspensivos de la canalización y, a continuación, especifique una cadena que contenga los valores de los separadores.