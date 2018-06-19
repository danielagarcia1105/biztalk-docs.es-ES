---
title: Actualización2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4376cae94e91f462974c626a57170b80b0117ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286764"
---
# <a name="update"></a><span data-ttu-id="1f21e-102">Update</span><span class="sxs-lookup"><span data-stu-id="1f21e-102">Update</span></span>
<span data-ttu-id="1f21e-103">El elemento `Update` se usa para extraer datos de un evento y lo importa en la actividad de BAM relacionada.</span><span class="sxs-lookup"><span data-stu-id="1f21e-103">The `Update` element is used to extract data from an event and import it into the related BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="1f21e-104">Formato</span><span class="sxs-lookup"><span data-stu-id="1f21e-104">Format</span></span>  
 <span data-ttu-id="1f21e-105">Para usar el `Update` elemento, debe proporcionar un nombre de columna y el tipo y un **expresión** elemento que contiene uno o más **operación** elementos que se evalúan como un valor de cadena único.</span><span class="sxs-lookup"><span data-stu-id="1f21e-105">To use the `Update` element, you must provide both a column name and type and an **Expression** element containing one or more **Operation** elements that evaluate to a single string value.</span></span>  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a><span data-ttu-id="1f21e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="1f21e-106">Attributes</span></span>  
  
|<span data-ttu-id="1f21e-107">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="1f21e-107">Attribute name</span></span>|<span data-ttu-id="1f21e-108">Description</span><span class="sxs-lookup"><span data-stu-id="1f21e-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1f21e-109">ColumnName</span><span class="sxs-lookup"><span data-stu-id="1f21e-109">ColumnName</span></span>|<span data-ttu-id="1f21e-110">Nombre de punto de control de actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="1f21e-110">BAM activity checkpoint name.</span></span> <span data-ttu-id="1f21e-111">Éste es el punto de control que se actualizará con los datos extraídos.</span><span class="sxs-lookup"><span data-stu-id="1f21e-111">This is the checkpoint that will be updated with the extracted data.</span></span>|  
|<span data-ttu-id="1f21e-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="1f21e-112">Type</span></span>|<span data-ttu-id="1f21e-113">El tipo de datos de BAM del punto de control debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f21e-113">BAM data type of the checkpoint; must be one of the following:</span></span><br /><br /> <span data-ttu-id="1f21e-114">-NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="1f21e-114">-   NVARCHAR</span></span><br /><span data-ttu-id="1f21e-115">-FECHA Y HORA</span><span class="sxs-lookup"><span data-stu-id="1f21e-115">-   DATETIME</span></span><br /><span data-ttu-id="1f21e-116">-INT</span><span class="sxs-lookup"><span data-stu-id="1f21e-116">-   INT</span></span><br /><span data-ttu-id="1f21e-117">-FLOAT</span><span class="sxs-lookup"><span data-stu-id="1f21e-117">-   FLOAT</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f21e-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f21e-118">Remarks</span></span>  
 <span data-ttu-id="1f21e-119">Las siguientes operaciones no se admiten en la expresión `Update`:</span><span class="sxs-lookup"><span data-stu-id="1f21e-119">The following operations are not supported in the `Update` expression:</span></span>  
  
-   <span data-ttu-id="1f21e-120">And</span><span class="sxs-lookup"><span data-stu-id="1f21e-120">And</span></span>  
  
-   <span data-ttu-id="1f21e-121">Es igual a</span><span class="sxs-lookup"><span data-stu-id="1f21e-121">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f21e-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f21e-122">Example</span></span>  
 <span data-ttu-id="1f21e-123">En el ejemplo siguiente, la **GetContextProperty** operación WF se utiliza para recuperar la **EventTime** propiedad.</span><span class="sxs-lookup"><span data-stu-id="1f21e-123">In the following example, the **GetContextProperty** WF operation is used to retrieve the **EventTime** property.</span></span> <span data-ttu-id="1f21e-124">Este valor se almacenará como un **DATETIME** tipo para el elemento de datos "StartOrderProcessing" para la actividad de BAM.</span><span class="sxs-lookup"><span data-stu-id="1f21e-124">This value will be stored as a **DATETIME** type for the "StartOrderProcessing" data item for the BAM activity.</span></span>  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f21e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f21e-125">See Also</span></span>  
 [<span data-ttu-id="1f21e-126">Elemento OnEvent del interceptor</span><span class="sxs-lookup"><span data-stu-id="1f21e-126">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)