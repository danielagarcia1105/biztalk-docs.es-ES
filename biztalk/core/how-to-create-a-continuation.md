---
title: Cómo crear una continuación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities, relating events
- tracking profiles, relating events
- continuations, tracking profiles
- activities, continuations
- events, relating
- orchestrations, business events
- tracking profiles, updating
- activities, tracking profiles
- tracking profiles, continuations
- tracking profiles, connecting activities
ms.assetid: 31d6fc24-676e-418c-8e78-1a46b045905d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e63983b290f0f4d7dff544cd2faea45f6cf46adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248852"
---
# <a name="how-to-create-a-continuation"></a>Cómo crear una continuación
Se crean continuaciones para indicar qué eventos empresariales de una o varias orquestaciones están relacionados al construir actividades conectadas.  
  
> [!IMPORTANT]
>  La actualización de un perfil de seguimiento puede afectar a las instancias de actividad en ejecución si la actividad incluye una continuación de BAM. En concreto, si la actualización del perfil de seguimiento determina una intercepción descendente de datos para un elemento de actividad ya registrado, es posible que se sobrescriba el valor original. Fundamentalmente, una única secuencia de eventos no se verá afectada por la aplicación de las actualizaciones de perfiles de seguimiento, ya que cada objeto de la secuencia está unido a una versión determinada del perfil que ya existía cuando se inició la actividad o secuencia.  Sin embargo, ya que las continuaciones son el medio de correlacionar varias secuencias de eventos, las secuencias que todavía no hayan comenzado cuando se actualice el perfil, recogerán los cambios en las actualizaciones, lo que hace que sea posible la mencionada sobrescritura de datos.  
  
> [!NOTE]
>  Se pueden crear continuaciones con las orquestaciones que no procesan mensajes. Se puede obtener la misma funcionalidad que la que se obtiene con las orquestaciones que procesan mensajes si se pasan llamadas de mensajes en curso entre orquestaciones y si se utiliza API BAM para procesar la continuación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, deberá disponer de orquestaciones y definiciones de actividad de BAM a las que se pueda conectar.  
  
### <a name="to-create-a-continuation"></a>Para crear una continuación  
  
1.  Abra un perfil de seguimiento existente o cree un perfil de seguimiento nuevo. Para obtener información acerca de cómo crear un perfil de seguimiento, vea [cómo crear un perfil de seguimiento](../core/how-to-create-a-tracking-profile.md).  
  
2.  Identificar un *token de continuación* que es un fragmento de información exclusiva que está disponible para las dos actividades. Por ejemplo, si un **CreditHistory** actividad se activa por un mensaje enviado desde un **LoanProcess** actividad dentro de un **EquityLoan**orquestación, el campo Nº de la mensaje se puede usar como un token de continuación ya que es común a ambas actividades.  
  
3.  Haga clic en la actividad y, a continuación, seleccione **nueva Continuation** para crear una continuación (CreditHistory). Asigne un nombre al nodo de continuación que acaba de crear.  
  
4.  Desde la vista Programación de orquestación, seleccione el token de continuación que eligió en el paso 2, como el Nº de SS (en este caso, desde la acción Envío) y arrástrelo al nodo de continuación que creó en el paso 3.  
  
5.  Haga clic en la actividad y seleccione **nuevo ContinuationID** para crear un nodo de Id. de continuación. Asígnele un nombre que sea exactamente el mismo que eligió en le paso 3 y arrástrelo al nodo que contenga el elemento de datos correspondiente (en este caso, Nº de SS desde la acción Recepción).  
  
6.  En el **archivo**menú, haga clic en **Guardar como**para guardar el perfil de seguimiento como un archivo .btt a la base de datos de administración de BizTalk y para evitar sobrescribir los archivos existentes de btt.  
  
## <a name="see-also"></a>Vea también  
 [Nodos Continuation y ContinuationID](../core/continuation-and-continuationid-nodes.md)   
 [Creación de perfiles de seguimiento](../core/creating-tracking-profiles.md)