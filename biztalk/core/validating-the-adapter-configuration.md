---
title: Validar la configuración del adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7fa3af1fa0116f859f0d3f39f2235be38cbc0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008133"
---
# <a name="validating-the-adapter-configuration"></a><span data-ttu-id="72eba-102">Validar la configuración del adaptador</span><span class="sxs-lookup"><span data-stu-id="72eba-102">Validating the Adapter Configuration</span></span>
<span data-ttu-id="72eba-103">Al agregar la ubicación de recepción y el puerto de envío, le pedirá que configure las propiedades personalizadas en el **\<** <em>nombre de adaptador</em> **\> propiedades de transporte** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="72eba-103">While adding the receive location and send port, you will be asked to configure your custom properties in the **\<**<em>Adapter Name</em>**\> Transport Properties** dialog box.</span></span> <span data-ttu-id="72eba-104">Los archivos de esquema XSD del proyecto AdapterHarness definen estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="72eba-104">The XSD schema files in the AdapterHarness project define these properties.</span></span>  
  
 <span data-ttu-id="72eba-105">La validación del esquema de configuración se realiza en tres partes:</span><span class="sxs-lookup"><span data-stu-id="72eba-105">Validation of the configuration schema occurs in three parts:</span></span>  
  
1.  <span data-ttu-id="72eba-106">Al mostrar una configuración guardada, el marco de trabajo de adaptadores valida el documento XML guardado con respecto al esquema antes de cargar el documento en la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="72eba-106">When displaying a saved configuration, the Adapter Framework validates the saved XML document against the schema before loading the document into the property page.</span></span> <span data-ttu-id="72eba-107">El marco de trabajo asume que un documento que no es válido indica un cambio en la definición del esquema de configuración.</span><span class="sxs-lookup"><span data-stu-id="72eba-107">The framework assumes that a document that is not valid indicates a change in the configuration schema definition.</span></span> <span data-ttu-id="72eba-108">En la página de propiedades solo se cargan los documentos válidos.</span><span class="sxs-lookup"><span data-stu-id="72eba-108">Only valid documents get loaded into the property page.</span></span>  
  
2.  <span data-ttu-id="72eba-109">Al guardar una configuración, si el adaptador implementa la **IAdapterConfigValidation** interfaz, el marco de trabajo se pasa al adaptador el documento XML construido de serializar los datos de la página de propiedad.</span><span class="sxs-lookup"><span data-stu-id="72eba-109">When saving a configuration, if the adapter implements the **IAdapterConfigValidation** interface, the framework passes to the adapter the XML document constructed from serializing the property page data.</span></span> <span data-ttu-id="72eba-110">A continuación, el adaptador procesa el documento.</span><span class="sxs-lookup"><span data-stu-id="72eba-110">The adapter then processes the document.</span></span> <span data-ttu-id="72eba-111">Los errores deben producir excepciones que detecta el marco de trabajo y se muestran al usuario.</span><span class="sxs-lookup"><span data-stu-id="72eba-111">Any errors should produce exceptions that are caught by the framework and displayed to the user.</span></span> <span data-ttu-id="72eba-112">Cualquier valor que falte o que se genere se debe generar durante la validación.</span><span class="sxs-lookup"><span data-stu-id="72eba-112">Any missing or generated values should be generated during validation.</span></span> <span data-ttu-id="72eba-113">Mediante el \<browsable show = "false"\> decoración suprime que muestra una entrada en la cuadrícula de propiedades, aunque el valor aparece en la instancia XML.</span><span class="sxs-lookup"><span data-stu-id="72eba-113">Using the \<browsable show="false"\> decoration suppresses showing an entry in the property grid, even though the value appears in the XML instance.</span></span>  
  
3.  <span data-ttu-id="72eba-114">Al guardar una configuración antes de colocar el valor en la base de datos, el marco de trabajo valida de nuevo el documento XML con respecto al esquema.</span><span class="sxs-lookup"><span data-stu-id="72eba-114">When saving a configuration before placing the value into the database, the framework again validates the XML document against the schema.</span></span> <span data-ttu-id="72eba-115">Esto asegura que solo se almacenan los datos válidos.</span><span class="sxs-lookup"><span data-stu-id="72eba-115">This ensures that only valid data is persisted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72eba-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="72eba-116">See Also</span></span>  
 [<span data-ttu-id="72eba-117">Problemas de diseño del adaptador</span><span class="sxs-lookup"><span data-stu-id="72eba-117">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)