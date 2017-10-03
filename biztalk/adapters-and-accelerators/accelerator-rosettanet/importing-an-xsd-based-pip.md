---
title: Importar una PIP basado en XSD | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, importing
- XSD-based PIPs
- PIPs, XSD-based PIPs
ms.assetid: d12441d4-79bf-4c24-9360-4b78c1da0d34
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf0ced3dbb9404cd1c4b9c81e566f47b09c7d0b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="importing-an-xsd-based-pip"></a>Importar un PIP basado en XSD
Aunque la mayoría de los PIP proporcionados por RosettaNet.org se basan en el DTD, algunos PIP más recientes están basados en XSD. En el siguiente procedimiento se describe cómo importar los PIP basados en XSD.  
  
### <a name="to-import-an-xsd-based-pip"></a>Para importar un PIP basado en XSD  
  
1.  Descargue el archivo .zip del PIP basado en XSD de RosettaNet.org en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859) o de CIDX.org en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361). Extraiga los archivos del archivo .zip. Los archivos que necesita estarán en las subcarpetas de la carpeta XML.  
  
2.  Abra Visual Studio. Cree un proyecto de BizTalk.  
  
3.  Abra el Explorador de Windows y desplácese a la carpeta XML extraída en el paso 1. Seleccione la primera carpeta dentro de la carpeta XML, arrástrela al explorador de soluciones en Visual Studio y colóquela en el proyecto. Repita este paso con cada una de las subcarpetas incluidas en la carpeta XML, creando la misma estructura de carpetas en el proyecto.  
  
    > [!NOTE]
    >  En el caso de un PIP PIP7c7, entre estas carpetas se incluyen las carpetas Domain, Interchange, System y Universal. En este PIP, el proyecto debería contener las carpetas Domain, Interchange, System y Universal y su contenido.  
  
4.  Si hay un archivo .xsd en la carpeta System, selecciónelo en el Explorador de soluciones y cambie el espacio de nombres en la página de propiedades para que no contenga la cadena ".System". Por ejemplo, para el PIP PIP7c7, puede cambiar el espacio de nombres a "PIP7c7._System". Repita este paso con cada archivo .xsd de la carpeta System. Si no se cambia el espacio de nombres, aparecerá el siguiente error o uno similar:  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  Revise todos los archivos .xsd para asegurarse de que el \<esquema > TypeName y el nodo raíz TypeName no son idénticos. Por ejemplo, para un PIP PIP7C7 el archivo PartnerIdentification.xsd de la carpeta Universal tiene el TypeName 'Partneridentification' tanto para el \<esquema > (cuando PartnerIdentification.xsd se selecciona en el Explorador de soluciones) y también el Nodo raíz PartnerIdentification. Para corregir este problema, seleccione PartnerIdentification.xsd en el Explorador de soluciones y, después, en la página de propiedades cambie la propiedad TypeName para que no contenga el mismo TypeName que el nodo raíz PartnerIdentification. Por ejemplo, cambie el TypeName por "_PartnerIdentification". Si no realiza este paso, aparecerá el siguiente error al intentar generar el proyecto:  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  La columna Archivo en la lista de errores indicará qué archivos tienen este problema.  
  
6.  Genere e implemente el proyecto.