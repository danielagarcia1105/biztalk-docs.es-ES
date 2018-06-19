---
title: Crear un proyecto de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b584e3ab-e824-4977-b4ed-4fc197a6cf7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eead267abbb990933e6fd3150d099d07b007526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209716"
---
# <a name="creating-a-pipeline-project"></a>Crear un proyecto de canalización
Para crear un proyecto de canalización:  
  
1.  En Visual Studio, cree un nuevo proyecto de BizTalk.  
  
2.  Agregue un elemento de la canalización de recepción y un elemento de la canalización de envío al proyecto.  
  
3.  Abra el archivo ReceivePipeline.btp.  
  
4.  En el Diseñador de canalizaciones, abra el cuadro de herramientas.  
  
5.  Haga clic en el **cuadro de herramientas** expuesta y, a continuación, seleccione **elegir elementos**.  
  
6.  En la ventana Elegir elementos del cuadro de herramientas, haga clic en el **componentes de canalización** ficha y, a continuación, seleccione los siguientes componentes de canalización:  
  
    -   SwiftMXDisassembler  
  
    -   SwiftMXAssembler  
  
    -   Componente de codificador de SWIFT MXRR  
  
    -   Componente de descodificador MXRR SWIFT  
  
    -   Componente de resolución de entidades de correlación de SWIFT MXRR  
  
7.  Arrastre el **SwiftMXDisassembler** componente en el marcador de posición de desensamblador en la canalización de recepción.  
  
8.  En las propiedades del componente SwiftMXDisassembler, establezca el **BRE validación** propiedad como TRUE o FALSE dependiendo de si desea habilitar la validación de reglas de negocio en los mensajes entrantes. Establecer el **TransportHeaderRequired** propiedad como TRUE o FALSE dependiendo de si desea proporcionar encabezado de transporte de mensajes.  
  
9. Arrastre el componente descodificador de MXRR de Swift y resolución de entidad de Swift MXRR correlación en el decodificador y el marcador de posición de la resolución de entidad dentro de la canalización de recepción.  
  
10. Seleccione el **resolución de entidad de correlación de MXRR** en la canalización. En la ventana Propiedades de componente de canalización, establezca el **habilitar el registro de BAM para la conciliación** propiedad como TRUE o FALSE, dependiendo de si desea habilitar la conciliación de las respuestas SWIFT.  
  
11. Abra la **SendPipeline.btp** archivo, en el Diseñador de canalizaciones, abrir el **cuadro de herramientas**.  
  
12. En el cuadro de herramientas, arrastre el **SwiftMXAssembler** componente en el marcador de posición de ensamblador dentro de la canalización de envío.  
  
13. Arrastre el **Swift MXRR codificador** componente en los marcadores de posición de codificador de la canalización de envío.  
  
14. Seleccione el **resolución de entidad del codificador de MXRR** en la canalización y, a continuación, en la ventana Propiedades de componente de canalización, establezca las siguientes propiedades.  
  
15. Habilitar **registro de BAM para la conciliación** como TRUE o FALSE, según si desea habilitar la conciliación de las respuestas SWIFT.  
  
16. Establecer el **LAU necesario** como TRUE o FALSE, según si tiene que habilitar la firma del mensaje en SWIFT Alliance acceso (AAS).  
  
17. Si la propiedad LAU necesario se ha se ha establecido en TRUE, a continuación, proporcionar LAU clave primera parte y LAU clave segunda parte (los valores tienen que coincidir con los que se proporcionaron al configurar la AAS).  
  
18. Genere e implemente el proyecto.