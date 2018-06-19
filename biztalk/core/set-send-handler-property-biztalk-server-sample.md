---
title: Establecer la propiedad de controlador de envío (ejemplo de BizTalk Server) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- send handlers, properties
ms.assetid: eb6ae2f2-528f-44ec-bca4-f37006893ff2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f783f465feff207ae1759ea358b0b848ccc0f4c3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974586"
---
# <a name="set-send-handler-property-biztalk-server-sample"></a>Establecer la propiedad de controlador de envío (ejemplo de BizTalk Server)
El ejemplo para establecer propiedad de controlador de envío muestra cómo establecer la información de configuración de XML para un controlador de envío del Protocolo simple de transferencia de correo (SMTP).  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 La secuencia de comandos de Visual Basic Scripting Edition (VBScript) en el archivo de secuencia de comandos que constituye este ejemplo muestra cómo se realizan las siguientes operaciones mediante el proveedor WMI de BizTalk Server:  
  
-   A partir de un nombre de controlador de envío, consultar una lista de controladores de envío coincidentes.  
  
-   Establecer la información de configuración de XML para un controlador de envío de SMTP.  
  
-   Administrar errores tales como la devolución al usuario de información significativa.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 Los archivos de ejemplo se encuentran en la siguiente ubicación de SDK:  
  
 \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Set Property\ del controlador de envío  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Description|  
|---------------|-----------------|  
|En la carpeta \VBScript:<br /><br /> ConfigureSMTP.vbs|El archivo VBScript toma parámetros que especifican un controlador de envío de SMTP y una dirección de remite de correo electrónico.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
 El ejemplo para establecer propiedad de controlador de envío consta de un archivo único VBScript que no necesita generar o inicializar.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a>Para ejecutar el ejemplo para establecer propiedad de controlador de envío  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     \<*Ejemplos de ruta de acceso*\>\Admin\WMI\Set Property\VBScript\ del controlador de envío  
  
2.  Ejecute el archivo ConfigureSMTP.vbs mediante el programa cscript, de modo que se pase el siguiente argumento de línea de comandos:  
  
    -   **\<** ***SMTPServerName* \>.** El nombre del servidor SMTP que se usará para enviar correo.  
  
    -   **\<** ***FromEmailAddress* \>.** Una dirección de correo electrónico que se usará como remite.  
  
         Por ejemplo:  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a>Comentarios  
 Todas las tareas que puede realizar en la consola de administración de BizTalk Server pueden llevarse a cabo también mediante secuencias de comandos con acceso al modelo de objetos WMI de Windows.  
  
 El archivo de secuencias de comandos ConfigureSMTP.vbs contiene comentarios detallados con más explicaciones acerca de las operaciones que realiza. Para obtener más información, vea Instrumental de administración de Windows en [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).  
  
## <a name="see-also"></a>Vea también  
 [Admin\WMI (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)