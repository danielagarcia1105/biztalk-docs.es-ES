---
title: "¿Qué ocurre con los artefactos durante la instalación y desinstalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- uninstalling, artifacts
- artifacts, uninstalling
- installing, artifacts
- artifacts, installing
- uninstalling
ms.assetid: f7b5bd8b-bfdf-4536-ae64-fa98c4885be6
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6274c32656ddece5a0afd81317538126d48b2f89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-to-artifacts-during-installation-and-uninstallation"></a>¿Qué le sucede a los artefactos durante la instalación y desinstalación?
En esta tema se describe cómo BizTalk Server trata los artefactos basados en archivos que se incluyen en una aplicación de BizTalk al instalar y desinstalar la aplicación.  
  
> [!NOTE]
>  Los puertos de envío, los grupos de puertos de envío, las ubicaciones de recepción y los puertos de recepción no son artefactos basados en archivos y no se ven afectados por la instalación y desinstalación. Las orquestaciones, los esquemas, las asignaciones y las canalizaciones se implementan y administran como parte de los ensamblados de BizTalk que los contienen.  
  
-   **Ensamblado de BizTalk.** durante la instalación, el archivo de ensamblado de BizTalk se copia en la ruta de destino, si se especificó una al agregar el ensamblado a la aplicación. Asimismo, el ensamblado se instala en la caché de ensamblados global (GAC) si se indicó esta opción al agregar el ensamblado. Al desinstalar la aplicación, el archivo de ensamblado se elimina del sistema de archivos si existe allí, pero no se desinstala de la GAC, salvo si el programador incluyó una secuencia de comandos posterior al procesamiento en la aplicación para realizar esta operación. Si es necesario, puede desinstalar los ensamblados de BizTalk de la GAC de forma manual. Para obtener más información, consulte [cómo desinstalar un ensamblado de la GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4).  
  
-   **Ensamblado. NET.** durante la instalación, el archivo de ensamblado .NET se copia en la ruta de destino, si se especificó una al agregar el ensamblado a la aplicación. Asimismo, el ensamblado se instala en la GAC y en el Registro de Windows si se indicaron estas opciones al agregar el ensamblado. Al desinstalar la aplicación, el archivo de ensamblado se elimina del sistema de archivos si existe allí y no está en el Registro de Windows. El ensamblado no se quita de la GAC ni del Registro de Windows, salvo si el programador incluyó una secuencia de comandos posterior al procesamiento en la aplicación para realizar esta operación. Si es necesario, puede quitar los ensamblados de BizTalk de la GAC o del Registro de Windows de forma manual. Para obtener más información, consulte [cómo desinstalar un ensamblado de la GAC](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4) y [cómo quitar otros archivos y configuración para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
  
-   **Archivo.** durante la instalación, el archivo se copia en el sistema de archivos local, si se especificó una ruta de destino al agregar el archivo a la aplicación. Al desinstalar la aplicación, el archivo se elimina del sistema de archivos.  
  
-   **Certificado.** durante la instalación, el certificado se agrega al almacén de certificados Otras personas del equipo local. Al desinstalar la aplicación, no se quita el certificado, salvo si el programador incluyó una secuencia de comandos posterior al procesamiento en la aplicación para realizar esta operación. Si es necesario, puede quitar los certificados de forma manual. Para obtener más información, consulte [cómo quitar otros archivos y configuración para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
  
-   **Directorio virtual.** si el equipo en el que está instalada la aplicación tiene Internet Information Services (IIS), se crea el directorio virtual. Si ya existe un directorio virtual con el mismo nombre que use el puerto especificado, los recursos del directorio virtual en el archivo .msi de la aplicación se escriben en el directorio virtual existente, y la configuración de seguridad del directorio virtual existente no se cambia. Debe comprobar que esta configuración de seguridad es suficiente. Si el grupo de aplicaciones al que está enlazado el directorio virtual no existe en el equipo local cuando se instala la aplicación, el directorio virtual se enlaza al grupo de aplicaciones predeterminado.  
  
     Al desinstalar la aplicación, se eliminan el directorio virtual y los archivos correspondientes, salvo si el directorio virtual existía antes de la instalación o si se agregaron archivos al directorio virtual después de la instalación. En tal caso, solo se eliminan los archivos que se instalaron desde el archivo .msi de la aplicación. No se eliminan en cambio ni el directorio virtual ni los archivos que se agregaron a la aplicación después de instalarla. El directorio virtual únicamente se elimina si está vacío.  
  
-   **Componente COM.** durante la instalación, se agrega el componente COM al Registro de Windows, si se especificó esta opción al agregar el componente a la aplicación. Asimismo, el archivo se copia al sistema de archivos local, si se indicó una ubicación de destino al agregar el componente a la aplicación. Al desinstalar la aplicación, el componente COM no se quita del Registro de Windows ni del sistema de archivos, salvo si el programador incluyó una secuencia de comandos posterior al procesamiento en la aplicación para realizar esta función. Si es necesario, puede quitar los componentes COM del Registro de Windows y del sistema de archivos de forma manual. Para obtener más información, consulte [cómo quitar otros archivos y configuración para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
  
-   **Secuencias de comandos previas y posteriores al procesamiento.** durante la instalación, los archivos de secuencias de comandos se copian en el sistema de archivos local, si se especificó una ruta de destino al agregar el archivo a la aplicación. Las secuencias de comandos previas al procesamiento se ejecutan antes de que se importe o quite la aplicación, así como después de la desinstalación. Las secuencias de comandos posteriores al procesamiento se ejecutan después de que se importe o quite la aplicación, así como antes de la instalación. Al desinstalar la aplicación, se eliminan los archivos de secuencias de comandos del sistema de archivos. Sin embargo, si las secuencias de comandos previas o posteriores al procesamiento agregaron archivos al sistema de archivos, no se eliminan. Si es necesario, puede eliminar los archivos de forma manual. Para obtener más información, consulte [cómo quitar otros archivos y configuración para una aplicación de BizTalk](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).  
  
-   **Artefactos de BAM.** durante la instalación, los archivos de artefactos de BAM se copian en la ruta de destino especificada al agregar el artefacto a la aplicación. Los artefactos de BAM no se implementan cuando se instala la aplicación. Al desinstalar la aplicación, se eliminan los archivos de artefactos de BAM.  
  
## <a name="see-also"></a>Vea también  
 [Cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md)   
 [Cómo desinstalar una aplicación de BizTalk](../core/how-to-uninstall-a-biztalk-application.md)   
 [¿Qué ocurre con los artefactos durante la implementación de aplicaciones](../core/what-happens-to-artifacts-during-application-deployment.md)