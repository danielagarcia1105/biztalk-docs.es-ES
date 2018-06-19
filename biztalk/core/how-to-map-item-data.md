---
title: Cómo asignar datos de elemento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data extraction
- orchestrations, data extraction
- orchestrations, tracking profiles
- tracking profiles, orchestrations
- tracking profiles, data extraction
ms.assetid: ae8b395e-152a-4e08-af31-3c9276f52711
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdfd722e1610be02c06dd6e2a9597e13c0f1e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253956"
---
# <a name="how-to-map-item-data"></a>Cómo asignar datos de elemento
Los datos de elemento se asignan para definir la extracción de datos de una orquestación.  
  
> [!NOTE]
>  Debe asegurarse de asignar valores de tipo de datos que sean compatibles con los elementos de actividad al crear perfiles de seguimiento. Si los tipos de datos no son compatibles, recibirá un error en tiempo de ejecución de BAM.  
  
> [!NOTE]
>  Al asignar hitos, como marcas de fecha y hora, los datos asignados deberán corresponderse con la representación de cadena SQL de una marca de fecha y hora. Los datos DateTime con formato DateTime XML y estructura AAAA-MM-DDHHH:MM:SS.mmm-HH:MM no están admitidos  
>   
>  Por ejemplo, no se admitirá la siguiente cadena de fecha: 1999-05-31H13:20:00.000-05:00.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Definiciones de actividad de BAM y orquestaciones implementadas que se van a conectar  
  
### <a name="how-to-map-item-data"></a>Cómo asignar datos de elemento  
  
1.  Abra un perfil de seguimiento existente o cree uno nuevo. Para obtener más información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).  
  
2.  En el escenario, se importa una definición de actividad llamada LoanProcessBamDef. Contiene el **LoanProcess** nodo de actividad, con un cliente **SSN** como ActivityID. Para obtener más información, consulte [nodos actividad y ActivityID](../core/activity-and-activityid-nodes.md).  
  
3.  Asegúrese de que cada actividad tiene un ActivityID o un elemento de datos ContinuationID (por ejemplo, un Número de seguridad social de cliente) para realizar su seguimiento.  
  
4.  Asigne acciones de orquestación a la carpeta de eventos empresariales que corresponda para indicar el evento cuyo seguimiento debe realizarse. Por ejemplo, en un escenario de procesamiento de préstamos los elementos siguientes, entre otros, se arrastrarán el **LoanProcess** carpeta de actividad:  
  
    -   **LoanApplicationReceived**  
  
    -   **CreditHistoryRequest**  
  
    -   **CreditHistoryResponse**  
  
## <a name="see-also"></a>Vea también  
 [Nodos de elemento de datos](../core/data-item-nodes.md)   
 [Creación de perfiles de seguimiento](../core/creating-tracking-profiles.md)