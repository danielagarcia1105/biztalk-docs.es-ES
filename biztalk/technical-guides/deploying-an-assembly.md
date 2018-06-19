---
title: Implementar un ensamblado | Documentos de Microsoft
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
ms.openlocfilehash: 73112fd9efb536452b8641faa976f42bb892b67c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297868"
---
# <a name="deploying-an-assembly"></a>Implementar un ensamblado
Implementar un ensamblado compila el ensamblado e importa, junto con las orquestaciones, canalizaciones, esquemas y mapas (artefactos) que contiene en la base de datos de administración de BizTalk local. Inicialmente, esto se hace en el entorno de desarrollo.  
  
 Implementación también asocia el ensamblado con la aplicación de BizTalk que ha especificado en las propiedades de proyecto en Visual Studio. Después de implementar una solución, puede ver y administrar los ensamblados implementados y sus artefactos desde la consola de administración de BizTalk Server o mediante la herramienta de la línea de comandos BTSTask. Puede administrar los artefactos individualmente o agrupados dentro de la aplicación.  
  
## <a name="deploying-an-assembly"></a>Implementar un ensamblado  
 Puede agregar ensamblados a las aplicaciones de las maneras siguientes:  
  
-   Implementar un ensamblado en una aplicación desde dentro del entorno de Visual Studio  
  
-   Agregar manualmente los ensamblados de BizTalk Server a la aplicación desde la consola de administración de BizTalk Server  
  
-   Agregar un ensamblado de BizTalk a una aplicación mediante el uso de secuencias de comandos desde la línea de comandos  
  
-   Mueva los ensamblados de BizTalk Server desde otras aplicaciones de la consola de administración de BizTalk Server  
  
 Para obtener más información acerca de cómo agregar ensamblados a las aplicaciones, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).  
  
## <a name="redeploying-assemblies"></a>Volver a implementar ensamblados  
 En el proceso de desarrollar y depurar los ensamblados de BizTalk, debe volver a implementarlos varias veces. BizTalk Server proporciona un mecanismo sencillo para volver a implementar. Si está volviendo a implementar un ensamblado sin cambiar el número de versión, puede usar la propiedad volver a implementar. BizTalk Server realizará automáticamente todos los pasos para volver a implementar el ensamblado.  
  
 Para obtener más información acerca de cómo volver a implementar ensamblados, vea [cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720).  
  
### <a name="best-practices-for-redeploying-an-assembly"></a>Prácticas recomendadas para volver a implementar un ensamblado  
 **Debe instalar al nuevo ensamblado en la GAC**  
  
-   Al implementar un ensamblado, siempre debe instalar la nueva versión del ensamblado en la caché de ensamblados global (GAC). Puede hacerlo una vez que lo ha vuelto a implementar. Para obtener más información, consulte [cómo instalar un ensamblado en la GAC](http://go.microsoft.com/fwlink/?LinkID=154828) (http://go.microsoft.com/fwlink/?LinkID=154828).  
  
 **Siempre debe implementar en el nivel de solución cuando existen dependencias**  
  
-   Si una solución cuenta con varios ensamblados y uno o varios tienen una dependencia en el ensamblado que desea volver a implantar, debe volver a implantar los ensamblados en el nivel de solución. Esto es porque cuando se vuelve a implementar un ensamblado en el nivel de proyecto, BizTalk Server se detenga, dar de baja, desenlace y quitará los artefactos en todos los ensamblados que ya sea dependen de este ensamblado o de que depende este ensamblado. BizTalk Server no llevará a cabo los pasos adicionales para implementar, enlazar, dar de alta e iniciar los artefactos. Sin embargo, al volver a implementar la solución completa, BizTalk Server lleva a cabo automáticamente todos los pasos necesarios para anular la implementación y volver a implementar todos los artefactos en la solución según sus dependencias.  
  
 **Puede que necesite volver a implementar manualmente los ensamblados dependientes**  
  
-   BizTalk Server siempre anula la implementación de ensamblados dependientes cuando anula la implementación de un ensamblado, pero en los casos siguientes, debe realizar los pasos adicionales para implementar, enlazar y dar de alta los artefactos en cada ensamblado dependiente después de volver a implementar el ensamblado en el que el en función de ensamblado:  
  
     Si vuelve a implementar un ensamblado en el nivel de proyecto y otro ensamblado de la misma solución depende de él.  
  
     Si vuelve a implementar un ensamblado en el nivel de solución, pero existe un ensamblado dependiente en una solución diferente.  
  
 **Debe reiniciar instancias de host**  
  
-   Al volver a implementar un ensamblado que contiene una orquestación sin cambiar el número de versión del ensamblado, el ensamblado existente se sobrescribe en la base de datos de Administración de BizTalk. Sin embargo, antes de que el cambio se haga efectivo, deberá reiniciar cada instancia de host correspondiente al host al que está enlazada la orquestación. Puede especificar la opción para que todas las instancias de host del equipo local se reinicien automáticamente al volver a implementar un ensamblado.  
  
     Al volver a implementar un ensamblado que contiene una orquestación sin cambiar el número de versión del ensamblado, el ensamblado existente se sobrescribe en la base de datos de Administración de BizTalk. Sin embargo, antes de que el cambio se haga efectivo, deberá reiniciar cada instancia de host correspondiente al host al que está enlazada la orquestación. Puede especificar la opción para que todas las instancias de host del equipo local se reinicien automáticamente al volver a implementar un ensamblado. Para obtener más información acerca de las propiedades de implementación, consulte [cómo establecer propiedades de implementación en Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154718) (http://go.microsoft.com/fwlink/?LinkID=154718).  
  
     Asimismo puede detener e iniciar cada instancia de host. Para obtener más información acerca de cómo detener e iniciar una instancia de host, consulte [cómo detener una instancia de Host](http://go.microsoft.com/fwlink/?LinkID=154829) (http://go.Microsoft.com/fwlink/?) LinkID = 154829) y [cómo iniciar una instancia de Host](http://go.microsoft.com/fwlink/?LinkID=154830) (http://go.Microsoft.com/fwlink/?) LinkID = 154830).