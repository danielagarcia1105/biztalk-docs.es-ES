---
title: Administrar (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, examples
- utilities, SSOMANAGE
- examples, SSO
- SSOMANAGE command line utility
ms.assetid: f738e344-4d81-4557-b399-68b59c413245
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15a94bf916550d9a2eada9b8f354432b4c154ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="manage-biztalk-server-sample"></a>Administrar (ejemplo de BizTalk Server)
El ejemplo para administrar inicio de sesión único (SSO) muestra cómo se construyen archivos .xml que se pueden usar con la utilidad de línea de comandos ssomanage.exe para llevar a cabo los siguientes tipos de operaciones de administración:  
  
-   Actualizar información global en el nivel de sistema de SSO.  
  
-   Crear aplicaciones afiliadas  
  
-   Crear asignaciones de usuarios  
  
 Para obtener información conceptual acerca de Enterprise Single Sign-On, vea [mediante SSO](../core/using-sso.md).  
  
 Para obtener un ejemplo que muestra cómo configurar mediante programación el SSO, como la creación de aplicaciones afiliadas y asignaciones de usuario, consulte [HTTPSSO (ejemplo de BizTalk Server)](../core/httpsso-biztalk-server-sample.md).  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo incluye pares de XSD y archivos .xml de ejemplo para cada uno de estos tipos de operaciones. Los valores de los archivos .xml de ejemplo no son válidos. Debe efectuar cambios en los valores para adecuarlos a sus necesidades específicas.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 *\<Ejemplos de ruta de acceso >*\SSO\Manage\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|AffiliateApplication.xml, GlobalInfo.xml, UserMapping.xml|Archivos .xml de ejemplo que puede, después de modificarlos, pasar como argumentos a la utilidad de línea de comandos ssomanage.exe.|  
|AffiliateApplication.xsd, GlobalInfo.xsd, UserMapping.xsd|Archivos de esquema para los archivos .xml correspondientes que proporcionan descripciones completas de sus posibles elementos y atributos. Puede usarlos para validar los archivos .xml correspondientes recibidos desde otros orígenes.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 Debido a que este ejemplo consta únicamente de archivos de lenguaje de definición de esquemas XML (XSD) y de archivos .xml, éstos últimos se pueden modificar y pasar a la utilidad de línea de comandos ssomanage.exe, no hay nada para crear.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Este ejemplo incluye archivos .xml de ejemplo para ejecutar la utilidad de línea de comandos ssomanage.exe en los tres modos diferentes que se indican a continuación:  
  
-   **Actualizar información global en el nivel de sistema SSO.** Para realizar este tipo de operación, efectúe los pasos siguientes:  
  
    1.  Edite el archivo GlobalInfo.xml como sea necesario para la configuración concreta.  
  
    2.  Ejecute la utilidad de línea de comandos ssomanage.exe con los argumentos adecuados, del modo siguiente:  
  
        ```  
        ssomanage –updatedb GlobalInfo.xml  
        ```  
  
     Asegúrese de que edita los valores en el archivo GlobalInfo.xml para que coincidan con el entorno. Por ejemplo, la cuenta de administrador de SSO debe ser una cuenta de Windows válida. Tanto la cuenta de administrador de SSO como la cuenta de administrador afiliado de SSO deben ser cuentas del grupo de dominios globales de Windows.  
  
-   **Crear aplicaciones afiliadas.** Para realizar este tipo de operación, efectúe los pasos siguientes:  
  
-   Edite el archivo AffiliateApplication.xml como sea necesario para la configuración concreta.  
  
    -   Ejecute la utilidad de línea de comandos ssomanage.exe con los argumentos apropiados, como se indica a continuación:  
  
        ```  
        ssomanage –createapps AffiliateApplication.xml  
        ```  
  
     Puede crear varias aplicaciones afiliadas al mismo tiempo.  
  
-   **Crear asignaciones de usuarios.** Para realizar este tipo de operación, efectúe los pasos siguientes:  
  
    1.  Edite el archivo UserMapping.xml como sea necesario para la configuración concreta.  
  
    2.  Ejecute la utilidad de línea de comandos ssomanage.exe con los argumentos apropiados, como se indica a continuación:  
  
        ```  
        ssomanage –createmappings UserMapping.xml  
        ```  
  
     Puede crear varias asignaciones para una o más aplicaciones afiliadas al mismo tiempo.  
  
## <a name="comments"></a>Comentarios  
 Después de realizar cambios en los archivos .xml de ejemplo proporcionados con este ejemplo, en concreto los cambios que implican incluir información confidencial en los archivos, asegúrese de que estos archivos están bien protegidos en su sistema de archivos. Por ejemplo, asegúrese de que no se colocan por equivocación en una carpeta de uso compartido.  
  
## <a name="see-also"></a>Vea también  
 [SSO (carpeta de ejemplos de BizTalk Server)](../core/sso-biztalk-server-samples-folder.md)