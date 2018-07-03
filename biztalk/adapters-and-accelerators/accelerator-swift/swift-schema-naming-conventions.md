---
title: Convenciones de nomenclatura de esquemas de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabd9796497bdd5b81d34f71c01124f26de203d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987429"
---
# <a name="swift-schema-naming-conventions"></a><span data-ttu-id="f3da0-102">Convenciones de nomenclatura de esquemas de SWIFT</span><span class="sxs-lookup"><span data-stu-id="f3da0-102">SWIFT Schema Naming Conventions</span></span>
<span data-ttu-id="f3da0-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye los esquemas para la sociedad para los mensajes FIN de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo que se crearon con el Editor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f3da0-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes schemas for Society for Worldwide Interbank Financial Telecommunication (SWIFT) FIN messages that were created using BizTalk Editor.</span></span> <span data-ttu-id="f3da0-104">Estos esquemas son compatibles con las siguientes convenciones a lo largo de:</span><span class="sxs-lookup"><span data-stu-id="f3da0-104">These schemas conform to the following conventions throughout:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3da0-105">Todos los esquemas tienen versiones.</span><span class="sxs-lookup"><span data-stu-id="f3da0-105">All schemas are versioned.</span></span> <span data-ttu-id="f3da0-106">Para ver la versión, abra [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y haga clic en el esquema en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="f3da0-106">To see the version, open [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and right-click the schema in Solution Explorer.</span></span> <span data-ttu-id="f3da0-107">Con el \<esquema\> nodo seleccionado en el Editor de BizTalk, en el panel Propiedades, desplácese a la propiedad versión estándar.</span><span class="sxs-lookup"><span data-stu-id="f3da0-107">With the \<Schema\> node selected in BizTalk Editor, in the Properties pane scroll down to the Standard Version property.</span></span>  
  
- <span data-ttu-id="f3da0-108">El nombre de cada archivo de esquema de intercambio es **MT*xxx*.xsd**, donde *xxx* es el tipo de mensaje FIN.</span><span class="sxs-lookup"><span data-stu-id="f3da0-108">The name of each interchange schema file is **MT*xxx*.xsd**, where *xxx* is the FIN message type.</span></span>  
  
- <span data-ttu-id="f3da0-109">Es el nombre del archivo de directiva principal asociado para cada mensaje **MT*xxx*_Master_Policy.xml**, y es el nombre correspondiente en el motor de reglas de negocios (BRE) **MT*xxx* _Master_Policy**, con un nombre de la lista de **MT*xxx*_PolicyList**.</span><span class="sxs-lookup"><span data-stu-id="f3da0-109">The name of the associated master policy file for each message is **MT*xxx*_Master_Policy.xml**, and the corresponding name in the Business Rule Engine (BRE) is **MT*xxx*_Master_Policy**, with a list name of **MT*xxx*_PolicyList**.</span></span>  
  
- <span data-ttu-id="f3da0-110">Es el nombre del archivo de directiva de validación asociado para cada mensaje **MT*xxx*_Validation_Policy.xml**, y es el nombre correspondiente en el BRE **MT*xxx*_Validation_Policy**.</span><span class="sxs-lookup"><span data-stu-id="f3da0-110">The name of the associated validation policy file for each message is **MT*xxx*_Validation_Policy.xml**, and the corresponding name in the BRE is **MT*xxx*_Validation_Policy**.</span></span>  
  
- <span data-ttu-id="f3da0-111">Dentro de cada esquema de mensaje, el nombre de la raíz es **SWIFT_CATEGORY*z*_MT*zxx*_Interchange**, donde *z* es el (categoría de mensaje primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f3da0-111">Within each message schema, the name of the root is **SWIFT_CATEGORY*z*_MT*zxx*_Interchange**, where *z* is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
- <span data-ttu-id="f3da0-112">El espacio de nombres de destino para cada esquema de mensaje **<http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx>** <em>, donde * z</em> es la categoría de mensaje (primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f3da0-112">The target namespace for each message schema is **<http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx>**<em>, where *z</em> is the message category (first digit of the message type) and *zxx* is the message type.</span></span>  
  
- <span data-ttu-id="f3da0-113">El tipo de documento es **MT * zxx**<em>, donde * zxx</em> es el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f3da0-113">The document type is **MT*zxx**<em>, where *zxx</em> is the message type.</span></span>  
  
- <span data-ttu-id="f3da0-114">Los nombres de campos que no están numerados y campos secundarios incluyen nombres descriptivos empresariales.</span><span class="sxs-lookup"><span data-stu-id="f3da0-114">The names of fields that are not numbered and sub-fields include descriptive business names.</span></span> <span data-ttu-id="f3da0-115">Se convierte en mayúsculas la primera letra de cada palabra y los nombres no incluyen un espacio intermedio o signos de puntuación entre palabras (por ejemplo, el nombre sería **ServiceIdentifier**, no **identificador del servicio**) .</span><span class="sxs-lookup"><span data-stu-id="f3da0-115">The first letter of each word is capitalized, and the names do not include an intervening space or punctuation between words (for example, the name would be **ServiceIdentifier**, not **Service Identifier**).</span></span>  
  
- <span data-ttu-id="f3da0-116">Las etiquetas de secuencias dentro de los mensajes se ajustan a la *Guía de referencia de SWIFT* (por ejemplo, **SequenceA**).</span><span class="sxs-lookup"><span data-stu-id="f3da0-116">The labels of sequences within messages conform to the *SWIFT Reference Guide* (for example, **SequenceA**).</span></span>  
  
- <span data-ttu-id="f3da0-117">Las etiquetas de numeran SWIFT campos incluyen un título descriptivo seguido de la secuencia (si existe), seguido por el código de número y el formato de letra opcional (por ejemplo, **Reference_A_20C**).</span><span class="sxs-lookup"><span data-stu-id="f3da0-117">The labels of numbered SWIFT fields include a descriptive title followed by the sequence (if present), followed by the number code and optional letter format (for example, **Reference_A_20C**).</span></span>  
  
- <span data-ttu-id="f3da0-118">Donde hay una opción de varios formatos para un campo, la etiqueta del nodo es  **\< *elección*\>**, y, a continuación, cada opción es un campo de número (por ejemplo, **fecha _A_98A** y **DateTime_A_98C**).</span><span class="sxs-lookup"><span data-stu-id="f3da0-118">Where there is a choice of multiple formats for a field, the label of the node is **\<*Choice*\>**, and then each option is a numbered field (for example, **Date_A_98A** and **DateTime_A_98C**).</span></span>  
  
- <span data-ttu-id="f3da0-119">El nombre de la definición de elemento de nivel más bajo de un subcampo consta del nombre del campo secundario seguido **tipo** (por ejemplo, **accountType** de cuenta).</span><span class="sxs-lookup"><span data-stu-id="f3da0-119">The name of the lowest level element definition of a sub-field consists of the name of the sub-field followed by **Type** (for example, **accountType** for Account).</span></span>  
  
  <span data-ttu-id="f3da0-120">Otros espacios de nombres en el esquema de mensaje incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3da0-120">Other namespaces in the message schema include the following:</span></span>  
  
- <span data-ttu-id="f3da0-121">xmlns: xs = "<http://www.w3.org/2001/XMLSchema>".</span><span class="sxs-lookup"><span data-stu-id="f3da0-121">xmlns:xs="<http://www.w3.org/2001/XMLSchema>".</span></span> <span data-ttu-id="f3da0-122">Este es el espacio de nombres del esquema XML de W3C de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f3da0-122">This is the default W3C XML Schema namespace.</span></span>  
  
- <span data-ttu-id="f3da0-123">xmlns: b = "<http://schemas.microsoft.com/BizTalk/2003>".</span><span class="sxs-lookup"><span data-stu-id="f3da0-123">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>".</span></span> <span data-ttu-id="f3da0-124">Este es el espacio de nombres de BizTalk predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f3da0-124">This is the default BizTalk namespace.</span></span>  
  
  <span data-ttu-id="f3da0-125">Cada esquema de mensaje directamente hace referencia al tipo base y los esquemas de tipo de datos comunes.</span><span class="sxs-lookup"><span data-stu-id="f3da0-125">Each message schema directly references the base type and common data type schemas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3da0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3da0-126">See Also</span></span>  
 [<span data-ttu-id="f3da0-127">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="f3da0-127">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)