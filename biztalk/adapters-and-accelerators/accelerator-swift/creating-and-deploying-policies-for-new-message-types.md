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
ms.openlocfilehash: b89972b2b84927fc16b14184338ca4920e984656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-deploying-policies-for-new-message-types"></a><span data-ttu-id="39d56-102">Crear e implementar directivas para nuevos tipos de mensaje</span><span class="sxs-lookup"><span data-stu-id="39d56-102">Creating and Deploying Policies for New Message Types</span></span>
<span data-ttu-id="39d56-103">Para crear e implementar directivas para nuevos tipos de mensajes:</span><span class="sxs-lookup"><span data-stu-id="39d56-103">To create and deploy policies for new message types:</span></span>  
  
1.  <span data-ttu-id="39d56-104">Cree una carpeta con el nombre del tipo de mensaje dentro de la carpeta mensajes MX.</span><span class="sxs-lookup"><span data-stu-id="39d56-104">Create a folder with the name of the message type inside MX Messages folder.</span></span> <span data-ttu-id="39d56-105">Por ejemplo, en este caso el nombre de la carpeta sería setr.004.001.02.</span><span class="sxs-lookup"><span data-stu-id="39d56-105">For example, in this case the name of the folder would be setr.004.001.02.</span></span>  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  <span data-ttu-id="39d56-106">Coloque el archivo de esquema (*.xsd) junto con el patrón resultante / directiva de validación de archivo para este tipo de mensaje en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="39d56-106">Place the schema file (*.xsd) along with the resulting master / validation policy file for this message type in this folder.</span></span>  
  
3.  <span data-ttu-id="39d56-107">Actualiza el MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools) con un nombre de la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="39d56-107">Update the MXMessageTypeKeywordList.xml (C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools) with a keyword name.</span></span> <span data-ttu-id="39d56-108">Este nombre debe ser las cuatro primeras letras del nombre de la carpeta de mensaje.</span><span class="sxs-lookup"><span data-stu-id="39d56-108">This name must be the first four letters of the message folder name.</span></span> <span data-ttu-id="39d56-109">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="39d56-109">For example,</span></span>  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  <span data-ttu-id="39d56-110">Para crear un patrón específico / las directivas de validación, realizar una copia del maestro / archivos de directivas de validación de las existentes de mensaje y lo coloca en la nueva carpeta de mensaje.</span><span class="sxs-lookup"><span data-stu-id="39d56-110">To create specific master / validation policies, take a copy of the master / validation policy files of the existing message and place it in the new message folder.</span></span>  
  
5.  <span data-ttu-id="39d56-111">Cambiar todas las referencias a tipos de mensajes en el maestro / directiva de validación para reflejar los nuevos tipos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="39d56-111">Change all of the references to message types in the master / validation policy to reflect the new message types.</span></span>  
  
## <a name="message-naming-conventions"></a><span data-ttu-id="39d56-112">Convenciones de nomenclatura de mensaje</span><span class="sxs-lookup"><span data-stu-id="39d56-112">Message Naming Conventions</span></span>  
 <span data-ttu-id="39d56-113">Siga estas convenciones para los nombres de mensaje:</span><span class="sxs-lookup"><span data-stu-id="39d56-113">Follow these conventions for message names:</span></span>  
  
-   <span data-ttu-id="39d56-114">**Reemplazar el nombre del mensaje**: si el nuevo nombre del mensaje es swift.if.ia.setr.004.001.02 y el mensaje anterior cuyos archivos de directivas se han usado es pacs.002.001.02, a continuación, reemplace todas las apariciones de pacs.002.001.02 con SWIFT.if.IA.setr.004.001.02 dentro de los archivos de directivas.</span><span class="sxs-lookup"><span data-stu-id="39d56-114">**Replacing the message name**: If the new message name is swift.if.ia.setr.004.001.02 and the old message whose policy files have been used is pacs.002.001.02, then replace all of the occurrences of pacs.002.001.02 with swift.if.ia.setr.004.001.02 within the policy files.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39d56-115">Nombre del mensaje es el nombre del archivo de esquema que se ha descargado y tipo de mensaje es el nombre del tipo de documento en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="39d56-115">Message name is the name of the schema file which has been downloaded and message type is the name of the document type in the message.</span></span>  
  
-   <span data-ttu-id="39d56-116">El nombre de los archivos de directivas de mantener el mismo que el propio esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="39d56-116">Keep the name of the policy files the same as the message schema itself.</span></span> <span data-ttu-id="39d56-117">Por ejemplo, swift.if.ia.setr.004.001.02.xsd tendrá siguiendo las directivas swift.if.ia.setr.004.001.02 _Master_Policy.xml y swift.if.ia.setr.004.001.02 _Validation_Policy.xml.</span><span class="sxs-lookup"><span data-stu-id="39d56-117">For example, swift.if.ia.setr.004.001.02.xsd will have following policies swift.if.ia.setr.004.001.02 _Master_Policy.xml and swift.if.ia.setr.004.001.02 _Validation_Policy.xml.</span></span>  
  
-   <span data-ttu-id="39d56-118">**Caracteres especiales**: si el nombre del mensaje tiene caracteres especiales en ella, la creación de un archivo de directiva requiere una convención ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="39d56-118">**Special characters**: If the message name has any special characters in it, then creating a policy file requires a slightly different convention.</span></span> <span data-ttu-id="39d56-119">Si el nombre del mensaje es, por ejemplo, swift.if.ia$setr.004.001.02, a continuación, debe cambiar el nombre del archivo de directiva para el nombre del mensaje con los caracteres especiales que se sustituye por "."</span><span class="sxs-lookup"><span data-stu-id="39d56-119">If the message name is, for example, swift.if.ia$setr.004.001.02, then you must change the name of the policy file to the message name with the special characters being replaced by “.”</span></span> <span data-ttu-id="39d56-120">Por ejemplo, si el nombre del archivo de esquema de mensaje es swift.if.ia$setr.004.001.02.xsd, la directiva principal resultante sería swift.if.ia.setr.004.001.02_Master_Policy.xml.</span><span class="sxs-lookup"><span data-stu-id="39d56-120">For example, if the name of the message schema file is swift.if.ia$setr.004.001.02.xsd, then the resulting master policy would be swift.if.ia.setr.004.001.02_Master_Policy.xml.</span></span>  
  
     <span data-ttu-id="39d56-121">El archivo de directiva principal también debe cambiarse para reflejar el nuevo nombre en las siguientes etiquetas:</span><span class="sxs-lookup"><span data-stu-id="39d56-121">The master policy file also needs to be changed to reflect the new name in the following tags:</span></span>  
  
    -   <span data-ttu-id="39d56-122">\<conjunto de reglas name="swift.if.ia.setr.004.001.02_Master_Policy" ></span><span class="sxs-lookup"><span data-stu-id="39d56-122">\<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"></span></span>  
  
    -   <span data-ttu-id="39d56-123">< regla name="swift.if.ia.setr.004.001.02_Policy_List"</span><span class="sxs-lookup"><span data-stu-id="39d56-123"><rule name="swift.if.ia.setr.004.001.02_Policy_List"</span></span>