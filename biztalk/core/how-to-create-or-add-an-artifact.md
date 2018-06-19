---
title: Cómo crear o agregar un artefacto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, creating
- applications, artifacts
ms.assetid: fea7487c-b5fa-457f-8c74-a20ea3a6df85
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b231cdf6a25c4ca316c9620ee789e6e3a715fd6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249492"
---
# <a name="how-to-create-or-add-an-artifact"></a>Cómo crear o agregar un artefacto
Tras crear una aplicación de BizTalk, puede agregar artefactos basados en archivo (por ejemplo, ensamblados de BizTalk, ensamblados de .NET, secuencias de comandos y certificados) desde el sistema de archivos o agregar directivas desde la base de datos del motor de reglas. También puede crear puertos de envío, grupos de puertos de envío, ubicaciones de recepción y puertos de recepción desde la aplicación. Al crear o agregar artefactos, estos se agregan a la base de datos de administración de BizTalk. Puede implementar la aplicación y sus artefactos como una sola entidad, como se describe en [implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md).  
  
> [!NOTE]
>  Ciertos tipos de artefactos deben ser únicos en una aplicación de BizTalk o un grupo. Para obtener más información, consulte [artefactos que deben ser únicos en una aplicación o un grupo de](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).  
  
 Para consultar los procesos para agregar o crear cada tipo de artefacto, consulte los siguientes temas:  
  
-   [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)  
  
-   [Cómo crear un grupo de puertos de envío](../core/how-to-create-a-send-port-group.md)  
  
-   [Cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md)  
  
-   [Cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md)  
  
-   [Cómo agregar una directiva a una aplicación](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [Cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [Cómo agregar una secuencia de comandos previa y posteriores al procesamiento a una aplicación](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [Cómo agregar un archivo a una aplicación](../core/how-to-add-a-file-to-an-application.md)  
  
-   [Cómo agregar un certificado a una aplicación](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [Cómo agregar un componente COM a una aplicación](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [Cómo agregar un ensamblado de .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [Cómo agregar un artefacto de BAM a una aplicación](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [Cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
> [!NOTE]
>  Si el artefacto que está agregando tiene un nombre de ruta de acceso muy largo (por ejemplo, el nombre de archivo y de ruta de acceso), se producirá un error en la operación de agregar el artefacto a la aplicación. Una ruta de acceso no puede tener más de 260 caracteres.  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)   
 [Cómo agregar un artefacto de 64 bits a una aplicación](../core/how-to-add-a-64-bit-artifact-to-an-application.md)