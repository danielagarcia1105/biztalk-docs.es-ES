---
title: Cómo construir una parte de mensaje Web desde un tipo de esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be8fd01e67309387749e7e512eca84bdb0f83db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984797"
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a><span data-ttu-id="010e7-102">Cómo construir una parte de mensaje Web a partir de un tipo de esquema</span><span class="sxs-lookup"><span data-stu-id="010e7-102">How to Construct a Web Message Part from a Schema Type</span></span>
<span data-ttu-id="010e7-103">Crear una parte de mensaje Web desde un tipo de esquema mediante el uso de un **transformar** forma.</span><span class="sxs-lookup"><span data-stu-id="010e7-103">You create a Web message part from a schema type by using a **Transform** shape.</span></span> <span data-ttu-id="010e7-104">Como alternativa, puede crear una parte de mensaje Web a partir de un tipo de esquema mediante la utilización de una clase .NET auxiliar para establecer las partes.</span><span class="sxs-lookup"><span data-stu-id="010e7-104">Alternatively, you can create a Web message part from a schema type by using a .NET helper class to set the parts.</span></span> <span data-ttu-id="010e7-105">Para obtener más información sobre cómo crear tipos de mensajes mediante el uso de una clase. NET, consulte [construir mensajes en código de usuario](../core/constructing-messages-in-user-code.md).</span><span class="sxs-lookup"><span data-stu-id="010e7-105">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a><span data-ttu-id="010e7-106">Para construir una parte de mensaje Web a partir de un tipo de esquema</span><span class="sxs-lookup"><span data-stu-id="010e7-106">To construct a Web message part from a schema type</span></span>  
  
1. <span data-ttu-id="010e7-107">Agregue una nueva asignación.</span><span class="sxs-lookup"><span data-stu-id="010e7-107">Add a new map.</span></span> <span data-ttu-id="010e7-108">Para obtener información sobre la creación de mapas, vea [cómo crear asignaciones nuevas](../core/how-to-create-new-maps.md).</span><span class="sxs-lookup"><span data-stu-id="010e7-108">For information about creating maps, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
2. <span data-ttu-id="010e7-109">En el asignador de BizTalk, haga clic en **Abrir esquema de destino** en el **esquema de destino** panel del mapa y, en el **selector de tipos de BizTalk** cuadro de diálogo, expanda el  **Esquemas** nodo, seleccione el esquema para la referencia Web agregada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="010e7-109">In BizTalk Mapper, click **Open Destination Schema** in the **Destination Schema** pane of the map and in the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the schema for the added Web reference, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="010e7-110">El formato del esquema de referencia Web es  **\<espacio de nombres predeterminado del proyecto\>.\< Nombre de referencia Web\>. Referencia**.</span><span class="sxs-lookup"><span data-stu-id="010e7-110">The format of the Web reference schema is **\<project default namespace\>.\<Web reference name\>.Reference**.</span></span>  
  
3. <span data-ttu-id="010e7-111">En el **nodo raíz para esquema de destino** cuadro de diálogo, seleccione un nodo raíz para el esquema de destino y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="010e7-111">In the **Root Node for Target Schema** dialog box, select a root node for the destination schema, and then click **OK**.</span></span> <span data-ttu-id="010e7-112">Para obtener más información sobre cómo determinar un nodo raíz para un tipo de parte de mensaje Web, consulte [cómo determinar un tipo de parte de mensaje Web](../core/how-to-determine-a-web-message-part-type.md).</span><span class="sxs-lookup"><span data-stu-id="010e7-112">For more information about how to determine a root node for a Web message part type, see [How to Determine a Web Message Part Type](../core/how-to-determine-a-web-message-part-type.md).</span></span>  
  
4. <span data-ttu-id="010e7-113">Haga clic en **Abrir esquema de origen** en el **esquema de origen** panel del mapa y, en el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquemas** nodo, seleccione el esquema de origen para asignar datos de y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="010e7-113">Click **Open Source Schema** in the **Source Schema** pane of the map and in the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the source schema to map data from, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="010e7-114">En el Asignador de BizTalk, cree vínculos entre el esquema de origen y el de destino.</span><span class="sxs-lookup"><span data-stu-id="010e7-114">In the BizTalk Mapper, create links between the source schema and target schema.</span></span>  
  
6. <span data-ttu-id="010e7-115">Abra una orquestación existente (o cree una nueva orquestación), abra el **cuadro de herramientas**y haga clic en el **orquestaciones de BizTalk** ficha.</span><span class="sxs-lookup"><span data-stu-id="010e7-115">Open an existing orchestration (or create a new orchestration), open the **Toolbox**, and click the **BizTalk Orchestrations** tab.</span></span>  
  
7. <span data-ttu-id="010e7-116">Arrastre un **construir mensaje** forma a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="010e7-116">Drag a **Construct Message** shape to the orchestration.</span></span>  
  
8. <span data-ttu-id="010e7-117">Editar el **mensaje construido** propiedad debe incluir el mensaje de instancia que ha creado para el tipo de mensaje Web.</span><span class="sxs-lookup"><span data-stu-id="010e7-117">Edit the **Message Constructed** property to include the message instance that yo created for the Web message type.</span></span>  
  
9. <span data-ttu-id="010e7-118">Arrastre un **transformar** dar forma a la **construir mensaje** dar forma y haga doble clic para abrir el **configuración de transformación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="010e7-118">Drag a **Transform** shape onto the **Construct Message** shape and double-click to open the **Transform Configuration** dialog box.</span></span>  
  
10. <span data-ttu-id="010e7-119">Haga clic en el **mapa existente** botón y seleccione la asignación que creó en el paso uno en el **nombre completo de asignación** cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="010e7-119">Click the **Existing Map** button and select the map that you created in step one in the **Fully Qualified Map Name** list box.</span></span>  
  
11. <span data-ttu-id="010e7-120">En el **transformar** panel, seleccione **origen**.</span><span class="sxs-lookup"><span data-stu-id="010e7-120">In the **Transform** pane, select **Source**.</span></span> <span data-ttu-id="010e7-121">En el **transformación del origen** panel, seleccione la instancia de un mensaje válido en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="010e7-121">In the **Source Transform** pane, select a valid message instance from the list box.</span></span>  
  
12. <span data-ttu-id="010e7-122">En el **transformar** panel, seleccione **destino**.</span><span class="sxs-lookup"><span data-stu-id="010e7-122">In the **Transform** pane, select **Destination**.</span></span> <span data-ttu-id="010e7-123">En el **transformación de destino** panel, seleccione el mensaje Web de instancia en el cuadro de lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="010e7-123">In the **Destination Transform** pane, select the Web message instance from the list box, and then click **OK**.</span></span>  
  
    <span data-ttu-id="010e7-124">Para obtener más información sobre el uso de la **configuración de transformación** cuadro de diálogo, vea [cómo configurar la forma transformación](../core/how-to-configure-the-transform-shape.md).</span><span class="sxs-lookup"><span data-stu-id="010e7-124">For more information about using the **Transform Configuration** dialog box, see [How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md).</span></span>  
  
    <span data-ttu-id="010e7-125">También puede usar este procedimiento para asignar la instancia de mensaje de respuesta del método Web a otra instancia de mensaje Web.</span><span class="sxs-lookup"><span data-stu-id="010e7-125">You can also use this procedure to map the Web method response message instance to another Web message instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="010e7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="010e7-126">See Also</span></span>  
 [<span data-ttu-id="010e7-127">Construcción de mensajes web</span><span class="sxs-lookup"><span data-stu-id="010e7-127">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)