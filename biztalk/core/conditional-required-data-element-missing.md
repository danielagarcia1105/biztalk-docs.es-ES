---
title: Falta un elemento de datos requerido condicional | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5105c03-fa26-4c38-a276-c656f3076d5f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43ebf2ba593ad5133b93400bf0e9cb1151dc45b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978445"
---
# <a name="conditional-required-data-element-missing"></a>Falta un elemento de datos requerido condicional.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                 X12DeConditionalRequiredDataElementMissingDescription                  |
|  Texto del mensaje   |                       Falta un elemento de datos requerido condicional.                        |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio entrante porque no existe en el intercambio un elemento de datos requerido por la regla X12ConditionDesignatorX.  
  
## <a name="user-action"></a>Acción del usuario  
 Este error se debe probablemente a un problema del intercambio entrante y no de la configuración o el funcionamiento de BizTalk Server. Para resolver este error, póngase en contacto con el remitente del intercambio e indique que debe cambiar los caracteres usados en él o bien el juego de caracteres identificado en el campo UNB1.1 para que coincidan.