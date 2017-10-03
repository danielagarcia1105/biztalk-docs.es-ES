---
title: "¿Qué ocurre cuando se importan artefactos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing, artifacts
- artifacts, importing
ms.assetid: a83957df-6e16-419a-b693-87985b498cc4
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d87e814fd43545d18db0d6e4fd0c585279eb5261
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-happens-when-artifacts-are-imported"></a>¿Qué ocurre cuando se importan los artefactos?
En este tema se describe lo que sucede cuando se importan artefactos. Hay tres modos de importar artefactos, que se tratan en este tema:  
  
-   Importar artefactos de un archivo .msi de BizTalk a un grupo o a una aplicación de BizTalk  
  
-   Importar un archivo de directiva .xml a un grupo de BizTalk  
  
-   Importar un archivo de enlace a un grupo o a una aplicación de BizTalk  
  
## <a name="importing-a-biztalk-msi-file"></a>Importar un archivo .msi de BizTalk  
 Al importar un archivo .msi de BizTalk a un grupo o a una aplicación de BizTalk, BizTalk Server controla los artefactos que contiene de la manera siguiente:  
  
-   Si durante la importación se agregaron referencias de esta aplicación a otras aplicaciones del grupo, se agrega la referencia a la base de datos de administración de BizTalk.  
  
-   Si especificó esta opción, los artefactos del archivo .msi que tienen el mismo nombre completo y número de versión (si es de aplicación) que los artefactos existentes en la aplicación sobrescriben a estos últimos.  
  
-   Si se han agregado archivos de enlace a la aplicación y seleccionó su entorno de destino durante la importación, los enlaces se aplican.  
  
-   Se ejecutarán secuencias de comandos previas y posteriores al procesamiento que estén configuradas para hacerlo durante la importación.  
  
-   Los datos de artefactos basados en archivos se serializan y almacenan en la base de datos de administración de BizTalk. Esto incluye datos para ensamblados, directorios virtuales, archivos, scripts, certificados y artefactos de BAM.  
  
    > [!IMPORTANT]
    >  Por razones de seguridad, cuando se exporta un certificado, se quita la clave privada. Por lo tanto, no se almacena ninguna clave privada en la base de datos de administración de BizTalk.  
  
-   Los datos de directivas se almacenan en la base de datos del motor de reglas.  
  
-   Los artefactos de BAM se almacenan en la base de datos de importación principal de BAM. Se implementan las definiciones de BAM.  
  
-   Los ensamblados de BizTalk y los de .NET que tengan configurada la opción de implementación para agregarse a la GAC durante la importación se agregan a la caché de ensamblados global (GAC).  
  
> [!NOTE]
>  Dado que los datos de artefactos están almacenados en las bases de datos de BizTalk Server, cuando exporte posteriormente la aplicación a un archivo .msi, BizTalk Server puede recuperar de las bases de datos toda la información de configuración así como los datos asociados a la aplicación y a sus artefactos, e incluirlos en el archivo .msi. Cuando importe el archivo .msi a otro grupo de BizTalk, toda la información de configuración de los artefactos y los datos vuelven a crearse en el grupo nuevo.  
  
 Después de importar una aplicación, puede ver, administrar e implementar los artefactos de la aplicación ya sea juntos, como una entidad única, o individualmente mediante la consola de administración o BTSTask. Para obtener más información, consulte [implementación de aplicaciones y herramientas de administración](../core/application-deployment-and-management-tools.md).  
  
## <a name="importing-a-policy"></a>Importar una directiva  
 Al importar una directiva desde un archivo .xml, se agrega a la base de datos del motor de reglas. Al contrario de lo que ocurre cuando importa una directiva en un archivo .msi de BizTalk, ésta no se asocia con ninguna aplicación de la base de datos de administración de BizTalk. La directiva se muestra en el nodo de directivas de la \<todos los artefactos > carpeta en la consola de administración de BizTalk Server. Después de haber importado la directiva, puede publicarla para que esté disponible para las aplicaciones en el grupo que vaya a usar. Para obtener más información, consulte [administrar directivas](../core/managing-policies.md).  
  
## <a name="importing-a-binding-file"></a>Importar un archivo de enlace  
 Al importar un archivo de enlace en un grupo de BizTalk, todos los enlaces que existan en ese momento en el grupo y que tengan el mismo nombre que los enlaces del archivo importado se sobrescribirán con los archivos de éste, y se aplicará la configuración.  
  
 Al importar un archivo de enlace en una aplicación de BizTalk, ya sea individualmente o como parte de una aplicación, todos los enlaces que existan en ese momento en la aplicación y que tengan el mismo nombre que los enlaces del archivo se sobrescribirán con los enlaces importados, y se aplicará la configuración.  
  
> [!IMPORTANT]
>  Por motivos de seguridad, cuando exporte un archivo de enlace, BizTalk Server quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción. Para obtener instrucciones, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Vea también [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué ocurre con los artefactos durante la implementación de aplicaciones](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [Importación de directivas, los enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [Implementación de aplicaciones y dependencias](../core/dependencies-and-application-deployment.md)