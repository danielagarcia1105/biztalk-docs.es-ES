---
title: Administrar ensamblados. NET, certificados y otros recursos | Documentos de Microsoft
description: Vínculos para agregar archivos de enlace, certificados, ensamblados, directorios virtuales, archivos y más información en el servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efe27a11-19d8-4eb3-9f8c-f4336e4c3d66
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb74762bdf08e6e9e2a79650a26dedb0915ea8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262732"
---
# <a name="manage-net-assemblies-certificates-and-other-resources"></a>Administrar ensamblados. NET, certificados y otros recursos

## <a name="overview"></a>Información general
Esta sección proporciona instrucciones sobre cómo usar la consola de administración de BizTalk Server y la herramienta de línea de comandos BTSTask para administrar los siguientes tipos de artefactos de recursos para una aplicación de BizTalk. Estos artefactos de recursos no se pueden implementar automáticamente en una aplicación de BizTalk desde Visual Studio; por tanto, se deben agregar de forma manual a la aplicación. Sin embargo, una vez agregados a una aplicación, se pueden importar, exportar e instalar como una unidad junto con la aplicación y sus demás artefactos.  
  
-   **Los archivos.** puede incluir archivos ad hoc, como archivos Léame. Al instalar la aplicación, los archivos se copian en la carpeta de instalación.  
  
-   **Certificados.** puede agregar un archivo de certificados a una aplicación, de modo que pueda transportar el certificado de un grupo de BizTalk a otro, empaquetado con una aplicación. Puede asignar certificados a los puertos de envío y las ubicaciones de recepción para comprobar las identidades y establecer vínculos seguros.  
  
-   **Componentes COM y COM +.** puede incluir componentes COM y COM+ administrados para proporcionar funcionalidad adicional en una aplicación de BizTalk.  
  
-   **Ensamblados. NET.** puede incluir ensamblados .NET que no sean específicamente ensamblados de BizTalk en una aplicación de BizTalk. Los ensamblados de BizTalk son ensamblados .NET que contienen orquestaciones, canalizaciones, esquemas o asignaciones de BizTalk.  
  
-   **Archivos de definición de BAM.** para facilitar la implementación de BAM, puede crear una aplicación de BizTalk y agregarle definiciones de BAM. Posteriormente, puede usar las características de implementación de aplicaciones de BizTalk para implementar las definiciones de BAM en distintos entornos.  
  
-   **Archivos de enlace.** puede agregar archivos de enlace a una aplicación para que el proceso de mover una aplicación de un entorno de desarrollo a otro sea más rápido y sencillo.  
  
-   **Directorios virtuales.** puede agregar directorios virtuales a las aplicaciones de modo que se implementen junto con la aplicación.  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Agregar un archivo a una aplicación](../core/how-to-add-a-file-to-an-application.md)  
  
-   [Agregar un certificado a una aplicación](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [Agregar un componente COM a una aplicación](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [Agregar un ensamblado de .NET a una aplicación](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [Agregar un artefacto de BAM a una aplicación](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [Agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
-   [Agregar un directorio Virtual para una aplicación](../core/how-to-add-a-virtual-directory-to-an-application.md)  
  
-   [Modificar las opciones de implementación de un ensamblado. NET, un componente COM, un archivo o un artefacto de BAM](../core/modify-deployment-options-of-net-assembly-com-component-file-bam-artifact.md)  
  
-   [Quitar un ensamblado. NET, certificado ni ningún otro artefacto de recurso de una aplicación](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)