---
title: Problemas conocidos con la validación y generación de esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df1eaa6c-0d3e-4aec-9de0-8b9817b7bb97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 298376e0d8e22e84964c2a70df165664f0da9b45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968221"
---
# <a name="known-issues-with-schema-generation-and-validation"></a><span data-ttu-id="9c42f-102">Problemas conocidos de validación y generación de esquema</span><span class="sxs-lookup"><span data-stu-id="9c42f-102">Known Issues with Schema Generation and Validation</span></span>
<span data-ttu-id="9c42f-103">En este tema se proporciona información acerca de los problemas conocidos relacionados con la generación y validación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="9c42f-103">This topic provides information about known issues with schema generation and validation.</span></span>  
  
## <a name="an-instance-message-generated-for-a-positional-record-with-tags-could-be-incorrect"></a><span data-ttu-id="9c42f-104">Un mensaje de instancia generado para un registro posicional con etiquetas puede ser incorrecto</span><span class="sxs-lookup"><span data-stu-id="9c42f-104">An instance message generated for a positional record with tags could be incorrect</span></span>  
 <span data-ttu-id="9c42f-105">En los registros posicionales, la etiqueta puede estar dentro de un campo o puede abarcar varios campos.</span><span class="sxs-lookup"><span data-stu-id="9c42f-105">For positional records, the tag can be within a field or can span between fields.</span></span> <span data-ttu-id="9c42f-106">En cualquier caso, la instancia generada no será válida y generará un error en el motor de análisis durante la fase de análisis.</span><span class="sxs-lookup"><span data-stu-id="9c42f-106">In either case, the instance generated will not be valid and will cause a failure in the Parsing Engine during the parsing stage.</span></span>  
  
 <span data-ttu-id="9c42f-107">Si la etiqueta no forma parte de ningún elemento secundario (registros o campos secundarios), no se producirá el problema.</span><span class="sxs-lookup"><span data-stu-id="9c42f-107">If the tag is not part of any children (child records or child fields), this problem will not occur.</span></span>  
  
 <span data-ttu-id="9c42f-108">Para solucionar este problema, incluya el valor real de las etiquetas como el valor predeterminado en el esquema.</span><span class="sxs-lookup"><span data-stu-id="9c42f-108">To work around this issue, include the actual value of the tag as the default in the schema.</span></span> <span data-ttu-id="9c42f-109">En la extensión de archivo sin formato del Editor de BizTalk, puede establecer el **valor fijo** o **Default Value** propiedad de campo posicional correspondiente con el valor de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9c42f-109">In the flat file extension of the BizTalk Editor, you can set the **Fixed Value** or **Default Value** property of the appropriate positional field with the value of the tag.</span></span>  
  
## <a name="an-instance-message-generated-for-a-field-with-some-restrictions-may-not-pass-validation"></a><span data-ttu-id="9c42f-110">Un mensaje de instancia generado para un campo con algunas restricciones puede no pasar la validación</span><span class="sxs-lookup"><span data-stu-id="9c42f-110">An instance message generated for a field with some restrictions may not pass validation</span></span>  
 <span data-ttu-id="9c42f-111">Al generar un mensaje de instancia de un esquema que contiene uno o varios **elemento de campo** y **atributo de campo** nodos que tienen tipos de datos que se han derivado mediante el mecanismo de restricción como Cuando el **patrón** se usa la propiedad, los datos de ejemplo generados para estos campos pueden no cumplir los requisitos de la restricción, lo que impide realizar correctamente la validación de ese mensaje de instancia mediante el mismo esquema de que se generó.</span><span class="sxs-lookup"><span data-stu-id="9c42f-111">When you generate an instance message from a schema that contains one or more **Field Element** and **Field Attribute** nodes that have data types that have been derived using the restriction mechanism, such as when the **Pattern** property is used, the sample data generated for such fields may not conform to the requirements of the restriction, thereby preventing successful validation of that instance message using the same schema from which it was generated.</span></span>  
  
## <a name="an-instance-message-generated-for-a-schema-that-contains-an-infinite-loop-may-not-be-valid"></a><span data-ttu-id="9c42f-112">Un mensaje de instancia generado para un esquema que contiene un bucle infinito puede no ser válido</span><span class="sxs-lookup"><span data-stu-id="9c42f-112">An instance message generated for a schema that contains an infinite loop may not be valid.</span></span>  
 <span data-ttu-id="9c42f-113">El esquema puede contener un bucle infinito cuando contiene una referencia circular a un nodo con un **Min Occurs** valor mayor o igual a uno, lo que impediría una condición de finalización de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9c42f-113">Your schema can contain an infinite loop when it contains a circular reference to a node with a **Min Occurs** property value greater than or equal to one, essentially preventing a termination condition.</span></span> <span data-ttu-id="9c42f-114">La generación de mensajes de instancia se finalizará de forma artificial para que la operación de generación pueda finalizar. No obstante, el mensaje de instancia generado no se ajustará al esquema desde el que se generó.</span><span class="sxs-lookup"><span data-stu-id="9c42f-114">Instance message generation will artificially terminate so that the generation operation can complete, but the produced instance message will thereby not conform to the schema from which it was generated.</span></span> <span data-ttu-id="9c42f-115">Dichos esquemas son normalmente sospechosos.</span><span class="sxs-lookup"><span data-stu-id="9c42f-115">Such schemas are usually suspect.</span></span>  
  
## <a name="validation-of-xml-instance-fails-for-document-schema-which-has-the-target-namespacehttpwwww3orgxml1998namespace"></a><span data-ttu-id="9c42f-116">Se produce un error de validación de instancia XML para el esquema de documento que tiene el espacio de nombres = "<http://www.w3.org/XML/1998/namespace>"</span><span class="sxs-lookup"><span data-stu-id="9c42f-116">Validation of XML instance fails for document schema which has the target namespace="<http://www.w3.org/XML/1998/namespace>"</span></span>  
 <span data-ttu-id="9c42f-117">El hipervínculo "<http://www.w3.org/XML/1998/namespace>" es un espacio de nombres reservado cuyo prefijo debería ser "XML".</span><span class="sxs-lookup"><span data-stu-id="9c42f-117">The HYPERLINK "<http://www.w3.org/XML/1998/namespace>" is a reserved namespace whose prefix should be “XML”.</span></span> <span data-ttu-id="9c42f-118">Puede modificar manualmente el prefijo a “XML”.</span><span class="sxs-lookup"><span data-stu-id="9c42f-118">You can manually edit the prefix to “XML”.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c42f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c42f-119">See also</span></span>
<span data-ttu-id="9c42f-120">Para obtener más detalles acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="9c42f-120">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
