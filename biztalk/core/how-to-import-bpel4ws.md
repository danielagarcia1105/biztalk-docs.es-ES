---
title: Cómo importar BPEL4WS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, restrictions
- BPEL4WS, importing
- BPEL4WS, orchestrations
- orchestrations, BPEL4WS
ms.assetid: 3626fcb9-8e7d-4812-a0c9-bde6e7954ec8
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b32a0044321ce6ac57d7bd49c14b40ba17430db
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-import-bpel4ws"></a><span data-ttu-id="4b8b6-102">Cómo importar BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4b8b6-102">How to Import BPEL4WS</span></span>
<span data-ttu-id="4b8b6-103">Puede importar desde el lenguaje BPEL4WS existente para crear una orquestación.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-103">You can import from existing BPEL4WS to create an orchestration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b8b6-104">Esta versión de BizTalk Server es compatible con BPEL4WS 1.1.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="4b8b6-105">No es compatible con BPEL4WS 1.0 para realizar importaciones o exportaciones.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="4b8b6-106">Para obtener un ejemplo de cómo importar BPEL4WS, consulte [BPEL importar (ejemplo de BizTalk Server)](../core/bpel-import-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="4b8b6-106">For an example of how to import BPEL4WS, see [BPEL Import (BizTalk Server Sample)](../core/bpel-import-biztalk-server-sample.md).</span></span>  
  
### <a name="to-import-bpel4ws-into-an-orchestration"></a><span data-ttu-id="4b8b6-107">Para importar BPEL4WS a una orquestación</span><span class="sxs-lookup"><span data-stu-id="4b8b6-107">To import BPEL4WS into an orchestration</span></span>  
  
1.  <span data-ttu-id="4b8b6-108">Cree un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-108">Create a new project.</span></span>  
  
2.  <span data-ttu-id="4b8b6-109">En los tipos disponibles en Proyecto de BizTalk, haga doble clic en Proyecto de importación BPEL de servidor BizTalk Server, o bien seleccione Proyecto de importación BPEL de servidor BizTalk Server y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-109">From the BizTalk Project types, double-click BizTalk Server BPEL Import Project, or select BizTalk Server BPEL Import Project and press OK.</span></span>  
  
3.  <span data-ttu-id="4b8b6-110">En el asistente, seleccione los archivos BPEL, WSDL y XSD que se deben importar para crear el nuevo proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-110">In the wizard, select the BPEL, WSDL and XSD files that should be imported to form the new BizTalk project.</span></span> <span data-ttu-id="4b8b6-111">Incluya todos los archivos a los que se hace referencia mediante las instrucciones import e include.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-111">Include all files that are referenced via import and include statements.</span></span>  
  
4.  <span data-ttu-id="4b8b6-112">Seleccione los archivos WSDL para los servicios Web invocados.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-112">Select WSDL files for invoked Web services.</span></span>  
  
     <span data-ttu-id="4b8b6-113">Ahora puede modificar o implementar la nueva orquestación.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-113">You can now modify or deploy the new orchestration.</span></span>  
  
 <span data-ttu-id="4b8b6-114">**Restricciones de importación de BPEL4WS**</span><span class="sxs-lookup"><span data-stu-id="4b8b6-114">**Import restrictions on BPEL4WS**</span></span>  
  
-   <span data-ttu-id="4b8b6-115">Al importar BPEL y WSDL, asegúrese de que la propiedad de nombre del nodo de definición WSDL y el nodo de proceso BPEL no coinciden.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-115">When importing BPEL and WSDL, make sure that the Name property of the WSDL definition node and the BPEL process node do not match.</span></span>  
  
-   <span data-ttu-id="4b8b6-116">No utilice palabras reservadas para XLANG/s en BPEL4WS cuando realice la importación.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-116">Do not use XLANG/s reserved words in BPEL4WS that you import.</span></span> <span data-ttu-id="4b8b6-117">Para obtener una lista completa, consulte [palabras reservadas de XLANG/s](../core/xlang-s-reserved-words.md).</span><span class="sxs-lookup"><span data-stu-id="4b8b6-117">For a complete list, see [XLANG/s Reserved Words](../core/xlang-s-reserved-words.md).</span></span>  
  
-   <span data-ttu-id="4b8b6-118">solo los tipos simples XSD predefinidos son compatibles.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-118">Only XSD predefined simple types are supported.</span></span>  
  
-   <span data-ttu-id="4b8b6-119">xsd: QName no es compatible; se importa como System.String.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-119">xsd:QName is not supported; it is imported as System.String.</span></span> <span data-ttu-id="4b8b6-120">Utilice en su lugar xsd: String.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-120">Use xsd:string instead.</span></span>  
  
-   <span data-ttu-id="4b8b6-121">Considere usar XPath canónicos al importar con BPEL4WS.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-121">Consider using canonical XPaths when importing BPEL4WS.</span></span>  
  
     <span data-ttu-id="4b8b6-122">Se recomienda importar solamente XPath canónicos para obtener un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-122">It is good practice to import only canonical XPaths in order to achieve optimal performance.</span></span> <span data-ttu-id="4b8b6-123">La ruta de acceso completa de la raíz al nodo promocionado se debe especificar mediante '/\*[local-name()="someName" y namespace-uri()="someUri"]'.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-123">The entire path from root to the promoted node must be spelled out by using '/\*[local-name()="someName" and namespace-uri()="someUri"]'.</span></span>  
  
     <span data-ttu-id="4b8b6-124">Si importa un XPath no canónico, puede quitar una promoción y volver a promocionar el mismo campo para que el editor de esquemas cree el XPath canónico correcto.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-124">If you import a non-canonical XPath, you can remove a promotion and repromote the same field in order to have the Schema Editor create the correct canonical XPath.</span></span>  
  
     <span data-ttu-id="4b8b6-125">Ejemplo: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span><span class="sxs-lookup"><span data-stu-id="4b8b6-125">Example: (targetNamespace = http://BizTalk_Server_Project3.Schema1)</span></span>  
  
    ```  
    <element name=Root type=complexType>  
                <sequence>  
                            <element name=promotedField/>  
                </sequence>  
    </element>  
    ```  
  
     <span data-ttu-id="4b8b6-126">XPath - / * [local-name () = 'Root' y el espacio ='http://BizTalk_Server_Project3.Schema1'] /\*[local-name () = 'promotedField' and espacio ='']</span><span class="sxs-lookup"><span data-stu-id="4b8b6-126">XPath - /*[local-name()='Root' and namespace-uri()='http://BizTalk_Server_Project3.Schema1']/\*[local-name()='promotedField' and namespace-uri()='']</span></span>  
  
    |<span data-ttu-id="4b8b6-127">XPath canónico</span><span class="sxs-lookup"><span data-stu-id="4b8b6-127">Canonical XPath</span></span>|<span data-ttu-id="4b8b6-128">XPath no canónico</span><span class="sxs-lookup"><span data-stu-id="4b8b6-128">Non-Canonical XPath</span></span>|  
    |---------------------|--------------------------|  
    |<span data-ttu-id="4b8b6-129">El Editor de BizTalk muestra un icono especial (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) para indicar que se ha promocionado el campo.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-129">BizTalk Editor displays a special icon (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) to denote that the field has been promoted.</span></span> <span data-ttu-id="4b8b6-130">El uso de expresiones XPath canónicas para promocionar campos mejora el rendimiento a través del recorrido más eficaz de XML.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-130">Usage of canonical XPath expressions to promote fields improves performance through more efficient traversal of the XML</span></span>|<span data-ttu-id="4b8b6-131">El Editor de BizTalk no muestra ningún icono especial.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-131">BizTalk Editor does not display a special icon.</span></span> <span data-ttu-id="4b8b6-132">Tanto el compilador como el cuadro de diálogo de promoción presentan advertencias.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-132">Both the compiler and the promotion dialog give warnings.</span></span> <span data-ttu-id="4b8b6-133">Hay un efecto lineal, aunque no trivial, sobre el rendimiento a medida que aumenta el tamaño del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4b8b6-133">There is a linear but nontrivial effect on performance as the message size increases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b8b6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b8b6-134">See Also</span></span>  
 <span data-ttu-id="4b8b6-135">[Cómo exportar BPEL4WS](../core/how-to-export-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="4b8b6-135">[How to Export BPEL4WS](../core/how-to-export-bpel4ws.md) </span></span>  
 [<span data-ttu-id="4b8b6-136">Conversiones de tipos de XLANG/s a BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4b8b6-136">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)