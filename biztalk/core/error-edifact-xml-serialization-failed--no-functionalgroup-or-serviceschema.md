---
title: Error de serialización Xml de intercambio EDIFACT debido a una estructura no válida, sin FunctionalGroup o ServiceSchema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 530faadd-e301-4743-b4b3-b04ba7578f1d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 370b9844faaa46955f6e45bfcea78f6eba0f8cf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003160"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-functionalgroup-or-serviceschema"></a>Error de serialización Xml de intercambio Edifact debido a una estructura no válida, sin FunctionalGroup o ServiceSchema
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| Versión del producto |                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    Identificador del evento     |                                                                      -                                                                       |
|  Origen del evento   |                            EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
|    Componente    |                                                                  Motor EDI                                                                  |
|  Nombre simbólico  |                                                                      -                                                                       |
|  Texto del mensaje   | Error de serialización Xml de intercambio Edifact debido a una estructura no válida. Se busca FunctionalGroup o ServiceSchema para UNZ, pero no se encuentra ninguno. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo procesar un intercambio EDIFACT procesado por lotes y conservado porque las etiquetas TransactionSetGroup o FunctionalGroup no se incluyeron en el archivo XML de intercambio.  
  
 Cuando BizTalk procesa un intercambio por lotes conservado, se asigna una etiqueta XML a un grupo de conjuntos de transacciones o a un grupo de los grupos del archivo XML del intercambio. A un grupo de grupos se le asigna la etiqueta FunctionalGroup. El indicador ServiceSchema indica el esquema de control usado para el intercambio de lotes conservados. Esta condición de error tiene lugar si configura un lote conservado mediante una canalización de recepción y una canalización de envío de transmisión de atravesar. La canalización de recepción configura las etiquetas y la de envío las elimina.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el archivo XML generado para el lote conservado tiene una estructura XML bien formada con la etiqueta FunctionalGroup (para varios grupos) o ServiceSchema (para el esquema de control usado para el intercambio por lotes conservado).