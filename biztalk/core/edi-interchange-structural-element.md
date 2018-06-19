---
title: Elemento estructural de intercambio EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03f47ae2-fa0f-4d88-a700-85f3d515d2d0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc07ae40a3665b47b446b61e24954ca9c588a6a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239532"
---
# <a name="edi-interchange-structural-element"></a>Elemento estructural de intercambio EDI
El intercambio es el elemento estructural de nivel más alto de un mensaje EDI. Consta de una colección de uno o más grupos intercambiados por dos socios comerciales. El destino de un intercambio debe ser un único socio comercial. Los intercambios pueden constar de conjuntos de transacciones/mensajes de uno o más tipos.  
  
 Con un intercambio, los encabezados definen el propio intercambio y los conjuntos de transacciones/mensajes y grupos dentro de éste. Los segmentos, elementos de datos y subelementos se delimitan mediante separadores. Cada separador tiene un valor predeterminado pero debe definirse como un carácter diferente para la entidad. En los intercambios de EDIFACT, los caracteres seleccionados para usar como separadores en el intercambio se definen en un encabezado de intercambio UNA independiente. En los intercambios de X12, los separadores se definen en el encabezado de intercambio ISA. Tenga en cuenta que, en X12, el separador de elementos de datos es el carácter en la cuarta posición, y el terminador de segmentos de datos es el carácter en la última posición. Los otros separadores de X12 y todos los separadores de EDIFACT se definen mediante campos, tal como el separador de componentes de X12, definido mediante el campo ISA16, y el separador de elementos de datos de EDIFACT, mediante el campo UNA2.  
  
 El intercambio incluye un sobre que define el mensaje EDI. El sobre debe comenzar con un encabezado de intercambio (ISA en X12 o UNA/UNB en EDIFACT) y debe acabar con un finalizador de intercambio (IEA/UNZ). El encabezado de intercambio incluye elementos que definen al remitente y al receptor, una fecha y una hora, un número de versión, un número de control que haga coincidir el encabezado con el finalizador y otra información.  
  
 Los campos ISA12 y GS8 (para intercambios X12) y el campo UNH2 (para intercambios EDIFACT) contienen información de versión que es necesaria para la detección de esquemas.  
  
 El finalizador de intercambio tiene un elemento que indica el número de grupos dentro del intercambio.  
  
> [!NOTE]
>  El encabezado de seguridad funcional y de control funcional, el segmento del valor de seguridad funcional y los segmentos de finalizador de seguridad funcional exceden el ámbito de EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si se recibe un intercambio con estos segmentos, se suspenderá con un registro de error que indica que los segmentos están sin identificar.