---
title: Crear e implementar directivas para nuevos tipos de mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43343238-ec45-44ed-a230-9e234bd22d05
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b826b3ee9408caf91fe5adcb2177d709f885a6e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="creating-and-deploying-policies-for-new-message-types"></a>Crear e implementar directivas para nuevos tipos de mensaje
Para crear e implementar directivas para nuevos tipos de mensajes:  
  
1.  Cree una carpeta con el nombre del tipo de mensaje dentro de la carpeta mensajes MX. Por ejemplo, en este caso el nombre de la carpeta sería setr.004.001.02.  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  Coloque el archivo de esquema (*.xsd) junto con el patrón resultante / directiva de validación de archivo para este tipo de mensaje en esta carpeta.  
  
3.  Actualiza el MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools) con un nombre de la palabra clave. Este nombre debe ser las cuatro primeras letras del nombre de la carpeta de mensaje. Por ejemplo,  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  Para crear un patrón específico / las directivas de validación, realizar una copia del maestro / archivos de directivas de validación de las existentes de mensaje y lo coloca en la nueva carpeta de mensaje.  
  
5.  Cambiar todas las referencias a tipos de mensajes en el maestro / directiva de validación para reflejar los nuevos tipos de mensaje.  
  
## <a name="message-naming-conventions"></a>Convenciones de nomenclatura de mensaje  
 Siga estas convenciones para los nombres de mensaje:  
  
-   **Reemplazar el nombre del mensaje**: si el nuevo nombre del mensaje es swift.if.ia.setr.004.001.02 y el mensaje anterior cuyos archivos de directivas se han usado es pacs.002.001.02, a continuación, reemplace todas las apariciones de pacs.002.001.02 con SWIFT.if.IA.setr.004.001.02 dentro de los archivos de directivas.  
  
    > [!NOTE]
    >  Nombre del mensaje es el nombre del archivo de esquema que se ha descargado y tipo de mensaje es el nombre del tipo de documento en el mensaje.  
  
-   El nombre de los archivos de directivas de mantener el mismo que el propio esquema de mensaje. Por ejemplo, swift.if.ia.setr.004.001.02.xsd tendrá siguiendo las directivas swift.if.ia.setr.004.001.02 _Master_Policy.xml y swift.if.ia.setr.004.001.02 _Validation_Policy.xml.  
  
-   **Caracteres especiales**: si el nombre del mensaje tiene caracteres especiales en ella, la creación de un archivo de directiva requiere una convención ligeramente diferente. Si el nombre del mensaje es, por ejemplo, swift.if.ia$setr.004.001.02, a continuación, debe cambiar el nombre del archivo de directiva para el nombre del mensaje con los caracteres especiales que se sustituye por "." Por ejemplo, si el nombre del archivo de esquema de mensaje es swift.if.ia$setr.004.001.02.xsd, la directiva principal resultante sería swift.if.ia.setr.004.001.02_Master_Policy.xml.  
  
     El archivo de directiva principal también debe cambiarse para reflejar el nuevo nombre en las siguientes etiquetas:  
  
    -   \<conjunto de reglas name="swift.if.ia.setr.004.001.02_Master_Policy"\>  
  
    -   < regla name="swift.if.ia.setr.004.001.02_Policy_List"