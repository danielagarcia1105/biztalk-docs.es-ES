---
title: La configuración del receptor de grupo no está configurada para el acuerdo del lote | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57b205e9-aaab-43d1-b373-17d206957814
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 534d426d192e27bbe7c6c7e866399b42360a8e3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990645"
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a>La configuración de receptor de grupo no está configurada para el acuerdo del lote
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| Versión del producto |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    Identificador del evento     |                                                                  -                                                                  |
|  Origen del evento   |                       EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                        |
|    Componente    |                                                           Motor de procesamiento por lotes                                                           |
|  Nombre simbólico  |                                                      GroupReceiverNotSelected                                                       |
|  Texto del mensaje   | La configuración del receptor de grupo no está configurada para el acuerdo del lote {0}. Debe configurarlos antes de que el procesamiento por lotes pueda continuar. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que ha tenido lugar una de estas dos condiciones:  
  
-   La orquestación por lotes no pudo validar un elemento de lote que ha recibido porque no se ha configurado el campo UNB1.1 (para un intercambio con la codificación EDIFACT) que contiene la sintaxis de codificación.  
  
-   La orquestación de lote no pudo crear la configuración de sobre para el elemento de lote porque las propiedades del encabezado no estaban completas (propiedades ISA, GS y ST para un intercambio X12 o propiedades UNA, UNB, UNG y UNH para un intercambio EDIFACT).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Si la orquestación por lotes no pudo validar un elemento de lote recibido porque la sintaxis de codificación no estaba configurada, configúrela para el campo UNB1.1 de la página Definición de segmento UNB del cuadro de diálogo Propiedades de EDI.  
  
-   Si la orquestación de lote no pudo crear la configuración de sobre para el elemento de lote porque las propiedades del encabezado no estaban completas, asegúrese de que estén configuradas las propiedades ISA, GS y ST para un intercambio X12 o las propiedades UNA, UNB, UNG y UNH para un intercambio EDIFACT.