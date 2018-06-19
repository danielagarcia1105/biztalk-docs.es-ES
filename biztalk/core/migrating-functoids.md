---
title: Migrar Functoids | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, migrating
- migrating, maps
- Migrating functoids, about Migrating functoids
- Migrating functoids
- Scripting functoids
- migrating, functoids
- migrating, Scripting functoids
ms.assetid: fc5b3ac9-28c6-41df-b779-15a8c3188528
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fac30a9b884bc769752623003d16e7089b140d4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009326"
---
# <a name="migrating-functoids"></a>Migrar functoids
Cuando se migra una asignación de versiones anteriores de BizTalk Server a BizTalk Server, también se migran todos los functoids incluidos en el mapa. Si no incluye los functoids que migra **secuencias de comandos** functoids, ninguna tarea de migración adicionales es necesaria. Sin embargo si la asignación incluye **secuencias de comandos** functoids personalizados o, tendrá que realice más pasos.  
  
 En versiones anteriores de BizTalk Server, incluido todo el script personalizado con un **secuencias de comandos** functoid se escribía en línea. Es decir, que cuando creó el functoid, todas las secuencias de comandos a las que llamó durante el tiempo de ejecución se almacenaron con el functoid. Si desea utilizar la misma secuencia de comandos con un functoid diferente, debe copiarlo y pegarlo de un **secuencias de comandos** functoid a otro, o se ha reescrito la secuencia de comandos desde el principio.  
  
 Al migrar una asignación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copia los scripts en línea existentes con los functoids. Sin embargo, no todas las secuencias de comandos funcionen correctamente. BizTalk Server utiliza Visual Basic .NET y JScript. NET, en lugar de VBScript y JScript usado en versiones anteriores. Las versiones .NET de los lenguajes incluyen algunos cambios en la sintaxis.  
  
> [!NOTE]
>  No olvide probar el **secuencias de comandos** functoids después de la migración.  
  
 Debe volver a escribir los functoids personalizados. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]espera functoids personalizados usen .NET framework. No puede utilizar los antiguos functoids personalizados basados en COM. Los functoids personalizados se pueden escribir para que utilicen .NET Framework. Para el código de ejemplo de un functoid personalizado, consulte [Functoid personalizado (ejemplo de BizTalk Server)](../core/custom-functoid-biztalk-server-sample.md).  
  
 Una alternativa consiste en ajustar la funcionalidad del functoid personalizado en un ensamblado externo y llamar a este ensamblado a través de un **secuencias de comandos** functoid. La siguiente sección describe este proceso:  
  
### <a name="to-migrate-your-custom-functoids"></a>Para migrar los functoids personalizados  
  
1.  Vuelva a crear la funcionalidad de un functoid en un lenguaje .NET, por ejemplo, Microsoft Visual Basic .NET, JScript .NET o Microsoft Visual C# .NET.  
  
2.  Cree un ensamblado que contenga la nueva funcionalidad.  
  
3.  Registre el ensamblado en la caché de ensamblados global (GAC).  
  
    > [!NOTE]
    >  Para registrar los ensamblados en la caché de ensamblados global, deben tener nombres seguros y estar firmados. Para obtener más información sobre el registro de ensamblados, vea "Caché global de ensamblados" en la colección combinada de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
4.  Crear una referencia entre la asignación que contiene el **secuencias de comandos** functoid y el ensamblado que contiene la funcionalidad que se ha vuelto a escribir.  
  
5.  Configurar la **Script** propiedad para la **secuencias de comandos** functoid. Esta propiedad determina qué script el **secuencias de comandos** functoid llamadas en tiempo de ejecución. Debe hacer coincidir el valor de esta propiedad con el lenguaje al que convirtió la secuencia de comandos personalizada. Para obtener más información sobre cómo configurar la propiedad de secuencia de comandos, consulte [editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md). Consulte también [Functoid de script](../core/scripting-functoid.md).  
  
6.  Compile el proyecto de BizTalk que contiene el mapa con la **secuencias de comandos** functoid.  
  
7.  Valide y pruebe la asignación.  
  
## <a name="see-also"></a>Vea también  
 [Editar propiedades de Functoid y parámetros de entrada](../core/editing-functoid-properties-and-input-parameters.md)   
 [Functoid de scripting](../core/scripting-functoid.md)