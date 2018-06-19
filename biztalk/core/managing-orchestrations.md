---
title: Administrar orquestaciones | Documentos de Microsoft
description: Vínculos para trabajar con orquestaciones de BizTalk Server, incluido el inicio, detener, enlazar, configurar, habilitar el seguimiento, suspender y mucho más
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cd12c202822c4d9ff849cc762b55e8f4880d80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262652"
---
# <a name="manage-orchestrations"></a>Administrar las orquestaciones

## <a name="overview"></a>Información general
En esta sección, se proporcionan instrucciones acerca de la utilización de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar orquestaciones. Una orquestación es un proceso empresarial ejecutable. Para obtener información general acerca de las orquestaciones, consulte [orquestaciones](../core/orchestrations.md).  

## <a name="add-to-application"></a>Agregar a la aplicación  
 Las orquestaciones se compilan [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk. No se puede agregar una orquestación a una aplicación de forma individual; una orquestación se agrega a una aplicación del modo siguiente:  
  
-   Al agregar un ensamblado de BizTalk que contiene una orquestación a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
-   Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene una orquestación, tal y como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
-   Cuando un programador implementa en una aplicación un ensamblado que contiene una orquestación de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  

## <a name="biztalk-administration-tasks"></a>Tareas de administración de BizTalk  
 La consola de administración se utiliza para llevar a cabo las acciones siguientes, tal como se describe en esta sección:  
  
-   Configurar enlaces para la orquestación enlazando la orquestación al host y a los puertos de recepción y envío apropiados, o quitar estos enlaces de la orquestación.  
  
-   Configurar el seguimiento de mensajes para la orquestación.  
  
-   Ver información de instancia de la orquestación.  
  
-   Dar de alta la orquestación en el host adecuado o darla de baja de éste.  
  
-   Iniciar o detener la orquestación para que inicie o detenga el procesamiento de mensajes.  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 
  
> [!NOTE]
>  El programador utiliza el Diseñador de orquestaciones para crear orquestaciones, como se describe en [crear orquestaciones utilizando Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md). El programador puede administrar orquestaciones durante el proceso de desarrollo mediante el uso de la consola de administración, como se describe en esta sección.  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Configurar enlaces para una orquestación](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [Separar una orquestación](../core/how-to-unbind-an-orchestration.md)  
  
-   [Configurar el seguimiento de una orquestación](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [Ver información de instancia para una orquestación](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [Quitar una orquestación de una aplicación](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [Dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md)  
  
-   [Dar de baja una orquestación](../core/how-to-unenlist-an-orchestration.md)  
  
-   [Iniciar una orquestación](../core/how-to-start-an-orchestration.md)  
  
-   [Detener una orquestación](../core/how-to-stop-an-orchestration.md)  
  
-   [Suspender, reanudar y finalizar instancias de orquestación](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [Actualizar una orquestación](../core/how-to-upgrade-an-orchestration.md)