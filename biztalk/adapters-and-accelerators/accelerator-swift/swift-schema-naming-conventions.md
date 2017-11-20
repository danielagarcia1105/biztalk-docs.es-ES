---
title: Convenciones de nomenclatura de esquema SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb792fe66e5806a186b0ffb946aa99f86a6a10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-schema-naming-conventions"></a><span data-ttu-id="87c75-102">Convenciones de nomenclatura de esquema SWIFT</span><span class="sxs-lookup"><span data-stu-id="87c75-102">SWIFT Schema Naming Conventions</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="87c75-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye los esquemas para la sociedad para los mensajes FIN de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo que se crearon con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="87c75-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes schemas for Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages that were created using BizTalk Editor.</span></span> <span data-ttu-id="87c75-104">Estos esquemas son compatibles con las siguientes convenciones a lo largo de:</span><span class="sxs-lookup"><span data-stu-id="87c75-104">These schemas conform to the following conventions throughout:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87c75-105">Todos los esquemas son con control de versiones.</span><span class="sxs-lookup"><span data-stu-id="87c75-105">All schemas are versioned.</span></span> <span data-ttu-id="87c75-106">Para ver la versión, abra [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y haga clic en el esquema en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="87c75-106">To see the version, open [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and right-click the schema in Solution Explorer.</span></span> <span data-ttu-id="87c75-107">Con el \<esquema > nodo seleccionado en el Editor de BizTalk, en el panel Propiedades, desplácese a la propiedad versión estándar.</span><span class="sxs-lookup"><span data-stu-id="87c75-107">With the \<Schema> node selected in BizTalk Editor, in the Properties pane scroll down to the Standard Version property.</span></span>  
  
-   <span data-ttu-id="87c75-108">El nombre de cada archivo de esquema de intercambio es  **MT*xxx*.xsd **, donde *xxx* es el tipo de mensaje FIN.</span><span class="sxs-lookup"><span data-stu-id="87c75-108">The name of each interchange schema file is **MT*xxx*.xsd**, where *xxx* is the FIN message type.</span></span>  
  
-   <span data-ttu-id="87c75-109">Es el nombre del archivo de directiva principal asociado para cada mensaje  **MT*xxx*_Master_Policy.xml**, y el nombre correspondiente en el motor de reglas de negocios (BRE) es   **MT*xxx*_Master_Policy**, con un nombre de la lista de  **MT*xxx*_PolicyList **.</span><span class="sxs-lookup"><span data-stu-id="87c75-109">The name of the associated master policy file for each message is **MT*xxx*_Master_Policy.xml**, and the corresponding name in the Business Rule Engine (BRE) is **MT*xxx*_Master_Policy**, with a list name of **MT*xxx*_PolicyList**.</span></span>  
  
-   <span data-ttu-id="87c75-110">Es el nombre del archivo de directiva de validación asociados para cada mensaje  **MT*xxx*_Validation_Policy.xml**, y es el nombre correspondiente en el BRE  **MT* xxx*_Validation_Policy**.</span><span class="sxs-lookup"><span data-stu-id="87c75-110">The name of the associated validation policy file for each message is **MT*xxx*_Validation_Policy.xml**, and the corresponding name in the BRE is **MT*xxx*_Validation_Policy**.</span></span>  
  
-   <span data-ttu-id="87c75-111">Dentro de cada esquema de mensaje, el nombre de la raíz es  **SWIFT_CATEGORY*z*_MT*zxx*_Interchange **, donde *z* es la categoría de mensaje (primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="87c75-111">Within each message schema, the name of the root is **SWIFT_CATEGORY*z*_MT*zxx*_Interchange**, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="87c75-112">El espacio de nombres de destino para cada esquema de mensaje  **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx***, donde *z* es la categoría de mensaje (primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="87c75-112">The target namespace for each message schema is **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx***, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="87c75-113">El tipo de documento es  **MT*zxx***, donde *zxx* es el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="87c75-113">The document type is **MT*zxx***, where *zxx* is the message type.</span></span>  
  
-   <span data-ttu-id="87c75-114">Los nombres de campos que no se numeran y subcampos incluyen nombres descriptivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="87c75-114">The names of fields that are not numbered and sub-fields include descriptive business names.</span></span> <span data-ttu-id="87c75-115">Se pone en mayúsculas la primera letra de cada palabra y los nombres no incluyen un espacio intermedio o signos de puntuación entre las palabras (por ejemplo, el nombre sería **ServiceIdentifier**, no **identificador del servicio de**) .</span><span class="sxs-lookup"><span data-stu-id="87c75-115">The first letter of each word is capitalized, and the names do not include an intervening space or punctuation between words (for example, the name would be **ServiceIdentifier**, not **Service Identifier**).</span></span>  
  
-   <span data-ttu-id="87c75-116">Las etiquetas de secuencias dentro de los mensajes se ajustan a la *Guía de referencia de SWIFT* (por ejemplo, **SequenceA**).</span><span class="sxs-lookup"><span data-stu-id="87c75-116">The labels of sequences within messages conform to the *SWIFT Reference Guide* (for example, **SequenceA**).</span></span>  
  
-   <span data-ttu-id="87c75-117">Las etiquetas de numeran SWIFT campos incluyen un título descriptivo seguido de la secuencia (si está presente), seguido por el código de número y el formato de letra opcional (por ejemplo, **Reference_A_20C**).</span><span class="sxs-lookup"><span data-stu-id="87c75-117">The labels of numbered SWIFT fields include a descriptive title followed by the sequence (if present), followed by the number code and optional letter format (for example, **Reference_A_20C**).</span></span>  
  
-   <span data-ttu-id="87c75-118">Si hay una selección de varios formatos para un campo, la etiqueta del nodo es  **\<* elección*> **, y, a continuación, cada opción es un campo de número (por ejemplo, **Date_A_98A** y **DateTime_A_98C**).</span><span class="sxs-lookup"><span data-stu-id="87c75-118">Where there is a choice of multiple formats for a field, the label of the node is **\<*Choice*>**, and then each option is a numbered field (for example, **Date_A_98A** and **DateTime_A_98C**).</span></span>  
  
-   <span data-ttu-id="87c75-119">El nombre de la definición de elemento de nivel más bajo de un subcampo consta del nombre del campo secundario seguido **tipo** (por ejemplo, **accountType** de cuenta).</span><span class="sxs-lookup"><span data-stu-id="87c75-119">The name of the lowest level element definition of a sub-field consists of the name of the sub-field followed by **Type** (for example, **accountType** for Account).</span></span>  
  
 <span data-ttu-id="87c75-120">Otros espacios de nombres en el esquema de mensaje son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="87c75-120">Other namespaces in the message schema include the following:</span></span>  
  
-   <span data-ttu-id="87c75-121">xmlns: xs = "http://www.w3.org/2001/XMLSchema".</span><span class="sxs-lookup"><span data-stu-id="87c75-121">xmlns:xs="http://www.w3.org/2001/XMLSchema".</span></span> <span data-ttu-id="87c75-122">Este es el espacio de nombres de esquema XML de W3C de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="87c75-122">This is the default W3C XML Schema namespace.</span></span>  
  
-   <span data-ttu-id="87c75-123">xmlns: b = "http://schemas.microsoft.com/BizTalk/2003".</span><span class="sxs-lookup"><span data-stu-id="87c75-123">xmlns:b="http://schemas.microsoft.com/BizTalk/2003".</span></span> <span data-ttu-id="87c75-124">Este es el espacio de nombres de BizTalk de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="87c75-124">This is the default BizTalk namespace.</span></span>  
  
 <span data-ttu-id="87c75-125">Cada esquema de mensaje directamente hace referencia al tipo base y los esquemas de tipo de datos comunes.</span><span class="sxs-lookup"><span data-stu-id="87c75-125">Each message schema directly references the base type and common data type schemas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c75-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="87c75-126">See Also</span></span>  
 [<span data-ttu-id="87c75-127">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="87c75-127">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)