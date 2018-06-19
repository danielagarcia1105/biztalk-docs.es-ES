---
title: Administración de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef1039fb-7460-444b-a45e-2783bdc7c109
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52e525499671a04228763c6792961c3204a3a2d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298676"
---
# <a name="managing-applications"></a>Administrar aplicaciones
Una aplicación de BizTalk es un contenedor lógico de artefactos de la aplicación, como orquestaciones, canalizaciones, esquemas, asignaciones y puertos. Aplicaciones de BizTalk le permiten incluir componentes relacionados en el mismo contenedor. Cualquier artefacto de una aplicación puede hacer referencia a los artefactos de la misma aplicación, o cualquier artefacto de cualquier aplicación que se hace referencia. Para obtener una lista completa de los artefactos que pueden estar en una aplicación de BizTalk, consulte [¿qué es una aplicación de BizTalk?](http://go.microsoft.com/fwlink/?LinkId=154994) (http://go.microsoft.com/fwlink/?LinkId=154994).  
  
 Aplicaciones de BizTalk simplifican muchos todos los días [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tareas. Puede implementar, administrar, iniciar, detener y solucionar problemas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el nivel de aplicación. Esto da como resultado menos confusión y menos riesgo de error para los usuarios. Contiene un contenedor de la aplicación de BizTalk  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ensamblados que se implementan en el el entorno de Visual Studio. La aplicación también puede contener puertos de recepción, ubicaciones de recepción, puertos de envío, configuración de seguimiento de propiedades y vínculos de función. Puede agregar manualmente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados a la aplicación, o mover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados desde otras aplicaciones. Además, puede agregar no -[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artefactos, como directivas de motor de reglas de negocios (BRE) y archivos de definición de BAM. Implícitamente, la aplicación también contiene todos los enlaces que se representan mediante su configuración actual.  
  
 Puede crear previo o secuencias de comandos posteriores al procesamiento para realizar acciones cuando se importa una aplicación, instalar o desinstalar. Para obtener más información acerca del uso de estas secuencias de comandos, consulte [mediante secuencias de comandos previas y posteriores al procesamiento para personalizar la implementación de aplicaciones](http://go.microsoft.com/fwlink/?LinkId=154995) (http://go.microsoft.com/fwlink/?LinkId=154995).  
  
 En esta sección se describe cómo implementar, versión y actualizar las aplicaciones o artefactos individuales.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Implementar una aplicación](../technical-guides/deploying-an-application.md)  
  
-   [Actualizar una aplicación](../technical-guides/updating-an-application.md)