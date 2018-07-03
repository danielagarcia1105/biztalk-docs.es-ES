---
title: Implementar un ensamblado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65f8ee21-0e52-4a74-b114-864a3069659c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fb363b6060b0c06436b36202100e855062c026f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984773"
---
# <a name="deploying-an-assembly"></a>Implementar un ensamblado
Implementar un ensamblado compila el ensamblado y los importa, junto con las orquestaciones, canalizaciones, esquemas y asignaciones (artefactos) que contiene en la base de datos de administración de BizTalk local. Inicialmente, esto se hace en el entorno de desarrollo.  
  
 Implementación también asocia el ensamblado con la aplicación de BizTalk que ha especificado en las propiedades de proyecto en Visual Studio. Después de implementar una solución, puede ver y administrar los ensamblados implementados y sus artefactos desde la consola de administración de BizTalk Server o mediante la herramienta de la línea de comandos BTSTask. Puede administrar los artefactos individualmente o agrupados dentro de la aplicación.  
  
## <a name="deploying-an-assembly"></a>Implementar un ensamblado  
 Puede agregar ensamblados a las aplicaciones de las maneras siguientes:  
  
- Implementar un ensamblado en una aplicación desde dentro del entorno de Visual Studio  
  
- Agregar manualmente los ensamblados de BizTalk Server a la aplicación desde la consola de administración de BizTalk Server  
  
- Agregar un ensamblado de BizTalk a una aplicación mediante el uso de secuencias de comandos desde la línea de comandos  
  
- Mover los ensamblados de BizTalk Server desde otras aplicaciones de la consola de administración de BizTalk Server  
  
  Para obtener más información acerca de cómo agregar ensamblados a las aplicaciones, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).  
  
## <a name="redeploying-assemblies"></a>Volver a implementar ensamblados  
 En el proceso de desarrollar y depurar los ensamblados de BizTalk, es posible que necesite volver a implementarlos varias veces. BizTalk Server proporciona un mecanismo sencillo para volver a implementarse. Si está volviendo a implementar un ensamblado sin cambiar el número de versión, puede usar la propiedad volver a implementar. BizTalk Server realizará automáticamente todos los pasos para volver a implementar el ensamblado.  
  
 Para obtener más información sobre cómo implementar ensamblados, vea [cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720).  
  
### <a name="best-practices-for-redeploying-an-assembly"></a>Prácticas recomendadas para volver a implementar un ensamblado  
 **Debe instalar al nuevo ensamblado en la GAC**  
  
- Al implementar un ensamblado, siempre debe instalar la nueva versión del ensamblado en la caché de ensamblados global (GAC). Puede hacerlo una vez que lo ha vuelto a implementar. Para obtener más información, consulte [cómo instalar un ensamblado en la GAC](http://go.microsoft.com/fwlink/?LinkID=154828) (http://go.microsoft.com/fwlink/?LinkID=154828).  
  
  **Siempre debe implementar en el nivel de solución cuando existen dependencias**  
  
- Si una solución cuenta con varios ensamblados y uno o varios tienen una dependencia en el ensamblado que desea volver a implantar, debe volver a implantar los ensamblados en el nivel de solución. Esto es porque cuando se vuelve a implementar un ensamblado en el nivel de proyecto, BizTalk Server se detenga, dar de baja, desenlazar y quitará los artefactos en todos los ensamblados que bien dependen de este ensamblado o de los que depende este ensamblado. BizTalk Server no llevará a cabo los pasos adicionales para implementar, enlazar, dar de alta e iniciar los artefactos. Sin embargo, al volver a implementar la solución completa, BizTalk Server lleva a cabo automáticamente todos los pasos necesarios para anular la implementación y volver a implementar todos los artefactos en la solución según sus dependencias.  
  
  **Es posible que deba implementar manualmente los ensamblados dependientes**  
  
- BizTalk Server siempre anula la implementación de ensamblados dependientes cuando anula la implementación de un ensamblado, pero en los casos siguientes, debe realizar los pasos adicionales para implementar, enlazar y dar de alta los artefactos en cada ensamblado dependiente después de volver a implementar el ensamblado en el que el éste depende:  
  
   Si vuelve a implementar un ensamblado en el nivel de proyecto y otro ensamblado de la misma solución depende de él.  
  
   Si vuelve a implementar un ensamblado en el nivel de solución, pero existe un ensamblado dependiente en una solución diferente.  
  
  **Debe reiniciar las instancias de host**  
  
- Al volver a implementar un ensamblado que contiene una orquestación sin cambiar el número de versión del ensamblado, el ensamblado existente se sobrescribe en la base de datos de Administración de BizTalk. Sin embargo, antes de que el cambio se haga efectivo, deberá reiniciar cada instancia de host correspondiente al host al que está enlazada la orquestación. Puede especificar la opción para que todas las instancias de host del equipo local se reinicien automáticamente al volver a implementar un ensamblado.  
  
   Al volver a implementar un ensamblado que contiene una orquestación sin cambiar el número de versión del ensamblado, el ensamblado existente se sobrescribe en la base de datos de Administración de BizTalk. Sin embargo, antes de que el cambio se haga efectivo, deberá reiniciar cada instancia de host correspondiente al host al que está enlazada la orquestación. Puede especificar la opción para que todas las instancias de host del equipo local se reinicien automáticamente al volver a implementar un ensamblado. Para obtener más información acerca de las propiedades de implementación, consulte [cómo establecer propiedades de implementación en Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154718) (http://go.microsoft.com/fwlink/?LinkID=154718).  
  
   También manualmente, se puede detener e iniciar cada instancia de host. Para obtener más información acerca de cómo detener e iniciar una instancia de host, consulte [cómo detener una instancia de Host](http://go.microsoft.com/fwlink/?LinkID=154829) (http://go.microsoft.com/fwlink/?LinkID=154829) y [cómo iniciar una instancia de Host](http://go.microsoft.com/fwlink/?LinkID=154830) (http://go.microsoft.com/fwlink/?LinkID=154830).