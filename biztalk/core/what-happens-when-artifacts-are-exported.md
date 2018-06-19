---
title: ¿Qué ocurre cuando se exportan artefactos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting, artifacts
- artifacts, exporting
ms.assetid: accc9a81-01fb-4da7-a5a5-167835d393a2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92a65889ea642706ae5c51849748fd8ad085a02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289388"
---
# <a name="what-happens-when-artifacts-are-exported"></a>¿Qué ocurre cuándo se exportan los artefactos?
Este tema describe lo que sucede cuando se exportan artefactos. Hay tres modos de exportar artefactos, que se tratan en este tema:  
  
-   Exportar una aplicación de BizTalk y sus artefactos a un archivo MSI de BizTalk (Windows Installer)  
  
-   Exportar una directiva a un archivo .xml  
  
-   Exportar enlaces a un archivo .xml  
  
## <a name="exporting-a-biztalk-application"></a>Exportar una aplicación de BizTalk  
 Al exportar una aplicación de BizTalk y los artefactos que contiene, la información de configuración de la aplicación y los datos de artefacto se exportan a un archivo MSI de BizTalk. La mayoría de los datos de artefacto se exportan desde la base de datos de administración de BizTalk, con las siguientes excepciones:  
  
-   Los datos de directivas se exportan desde la base de datos del motor de reglas del grupo.  
  
-   Los datos del directorio virtual se exportan desde la metabase de Internet Information Services (IIS), en caso de que no existan en la base de datos de administración. Este es el caso cuando el directorio virtual no se ha agregado expresamente a la aplicación (como se describe en [cómo agregar un directorio Virtual para una aplicación](../core/how-to-add-a-virtual-directory-to-an-application.md)) o la aplicación no se ha importado en este grupo desde un archivo .msi que se haya exportado desde otro grupo de BizTalk.  
  
-   Los datos del certificado se exportan desde el almacén de certificados Otras personas en el equipo local si no existe en la base de datos de administración. Este es el caso cuando el certificado no se ha agregado explícitamente a la aplicación (como se describe en [cómo agregar un certificado a una aplicación](../core/how-to-add-a-certificate-to-an-application.md)) o la aplicación no se ha importado en este grupo desde un archivo .msi que estaba exportar desde otro grupo de BizTalk. Los certificados se exportan al exportar una aplicación con un puerto de recepción que tiene un certificado asociado a él. Las claves privadas se quitan de los certificados al tener lugar la exportación.  
  
 Puede usar este archivo MSI para importar los artefactos de la aplicación, incluidos todos sus datos, en una aplicación de otro grupo de BizTalk. También puede usar este archivo MSI para instalar la aplicación en un equipo.  
  
## <a name="exporting-a-policy"></a>Exportar una directiva  
 Al usar la consola de administración para exportar una directiva para un grupo o una aplicación de BizTalk, se genera un archivo de directiva .xml que contiene la información de directiva. Puede importar este archivo de directiva en otro grupo de BizTalk para crear en él la directiva, de modo que las aplicaciones del grupo puedan usarla. Además, puede exportar información de directiva para una aplicación mediante el uso de BTSTask. Sin embargo, BTSTask no tiene un comando para exportar un archivo de directiva .xml. En su lugar, puede exportar un archivo MSI de aplicación que solo contiene la directiva. Es posible importar el archivo MSI en una aplicación de otro grupo.  
  
## <a name="exporting-bindings"></a>Exportar enlaces  
 Se puede usar la consola de administración o BTSTask para exportar enlaces para un grupo, una aplicación o un ensamblado de BizTalk. Al hacerlo, BizTalk Server genera un archivo .xml que contiene la información de enlace del grupo, de la aplicación o del ensamblado. Al exportar los enlaces, es posible exportar información global de entidad del grupo. Se puede agregar este archivo de enlace a una aplicación o importarlo en un grupo o una aplicación de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [¿Qué ocurre con los artefactos durante la implementación de aplicaciones](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [Exportar aplicaciones de BizTalk, los enlaces y directivas](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [Importación de directivas, los enlaces y las aplicaciones de BizTalk](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [Cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md)