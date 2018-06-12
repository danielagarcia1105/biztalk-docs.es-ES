---
title: SchemaValidator | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0291e5b901b6da3c19208f23846912ac16658ab6
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855471"
---
# <a name="schemavalidator"></a><span data-ttu-id="5615d-102">SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="5615d-102">SchemaValidator</span></span>
<span data-ttu-id="5615d-103">Utilice la utilidad SchemaValidator para solucionar problemas relacionados con una instancia de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5615d-103">You use the SchemaValidator utility to troubleshoot problems with a message instance.</span></span> <span data-ttu-id="5615d-104">Si recibe un mensaje que se produce un error de validación, puede ejecutar la utilidad SchemaValidator para determinar el origen del error.</span><span class="sxs-lookup"><span data-stu-id="5615d-104">If you receive a message that fails validation, you can run the SchemaValidator utility to determine the source of the failure.</span></span>  
  
 <span data-ttu-id="5615d-105">Use esta utilidad si usa un ensamblado que incluye un archivo .dll de esquema y no tiene un archivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="5615d-105">You use this utility if you are using an assembly that includes a schema .dll file, and you do not have a schema .xsd file.</span></span> <span data-ttu-id="5615d-106">La utilidad SchemaValidator le permite validar usando el archivo .dll de esquemas.</span><span class="sxs-lookup"><span data-stu-id="5615d-106">The SchemaValidator utility lets you validate using the schema .dll file.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="5615d-107">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="5615d-107">Location in SDK</span></span>  
 <span data-ttu-id="5615d-108">\<*unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="5615d-108">\<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator</span></span>  
  
## <a name="building-and-running-schemavalidator"></a><span data-ttu-id="5615d-109">Compilar y ejecutar SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="5615d-109">Building and Running SchemaValidator</span></span>  
  
#### <a name="to-build-the-schemavalidator-utility"></a><span data-ttu-id="5615d-110">Para generar la utilidad SchemaValidator</span><span class="sxs-lookup"><span data-stu-id="5615d-110">To build the SchemaValidator utility</span></span>  
  
1.  <span data-ttu-id="5615d-111">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="5615d-111">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="5615d-112">Mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator.</span><span class="sxs-lookup"><span data-stu-id="5615d-112">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
3.  <span data-ttu-id="5615d-113">En el símbolo del sistema, escriba **sn -k SchemaValidator.snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="5615d-113">At the command prompt, type **sn -k SchemaValidator.snk**, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="5615d-114">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="5615d-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
5.  <span data-ttu-id="5615d-115">En el **archivo** menú, elija **abiertos**y, a continuación, haga clic en **Abrir solución**.</span><span class="sxs-lookup"><span data-stu-id="5615d-115">On the **File** menu, point to **Open**, and then click **Open Solution**.</span></span>  
  
6.  <span data-ttu-id="5615d-116">Mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator, seleccione  **SchemaValidator.sln**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="5615d-116">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator, select **SchemaValidator.sln**, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="5615d-117">En el Explorador de soluciones, haga clic en **SchemaValidator**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5615d-117">In Solution Explorer, right-click **SchemaValidator**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="5615d-118">En la página **Propiedad de MessageInspector**  , haga clic en la ficha **Firma** y, a continuación, haga clic en la casilla **Firmar el ensamblado** .</span><span class="sxs-lookup"><span data-stu-id="5615d-118">In the **MessageInspector Property**  page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span> <span data-ttu-id="5615d-119">Seleccione **SchemaValidator.snk** en **elegir un archivo de clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="5615d-119">Select **SchemaValidator.snk** in **Choose a strong name key file**.</span></span>  
  
9. <span data-ttu-id="5615d-120">Haga clic en **SchemaValidator.cs**.</span><span class="sxs-lookup"><span data-stu-id="5615d-120">Click **SchemaValidator.cs**.</span></span>  
  
10. <span data-ttu-id="5615d-121">Escriba la ruta de acceso de la instancia de mensaje adecuado en la siguiente línea existente de código en `Main`:</span><span class="sxs-lookup"><span data-stu-id="5615d-121">Type the appropriate message instance path in the following existing line of code in `Main`:</span></span>  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. <span data-ttu-id="5615d-122">Reemplace la línea siguiente existente de código en `Main` con una referencia al ensamblado Rnpip y, a continuación, seleccione el esquema apropiado:</span><span class="sxs-lookup"><span data-stu-id="5615d-122">Replace the following existing line of code in `Main` with a reference to the RNPIPs assembly, and then select the appropriate schema:</span></span>  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. <span data-ttu-id="5615d-123">Haga clic en **SchemaValidator**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="5615d-123">Right-click **SchemaValidator**, and then click **Build**.</span></span>  
  
13. <span data-ttu-id="5615d-124">Modificar la instancia de mensaje al que desea probar mediante la eliminación de la \< \!DOCTYPE... \> etiqueta Especifica el archivo DTD desde el encabezado de la instancia XML.</span><span class="sxs-lookup"><span data-stu-id="5615d-124">Modify the message instance to you want to test by removing the \<\!DOCTYPE …\> tag specifying the DTD file from the header of the XML instance.</span></span>  
  
14. <span data-ttu-id="5615d-125">En el nodo raíz de la instancia de mensaje, agregue un espacio de nombres XML del esquema que se validarán ante.</span><span class="sxs-lookup"><span data-stu-id="5615d-125">In the root node of the message instance, add an XML namespace of the schema that you will validate against.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5615d-126">Para obtener un ejemplo de un esquema listo para ser validado por la utilidad SchemaValidator, vea Sample3A4.xml en \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\SchemaValidator.</span><span class="sxs-lookup"><span data-stu-id="5615d-126">For an example of a schema ready to be validated by the SchemaValidator utility, see Sample3A4.xml in \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator.</span></span>  
  
15. <span data-ttu-id="5615d-127">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **SchemaValidator.cs**y, a continuación, presione CTRL y F5 para ejecutar la utilidad.</span><span class="sxs-lookup"><span data-stu-id="5615d-127">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **SchemaValidator.cs**, and then press CTRL and F5 to run the utility.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5615d-128">Notas</span><span class="sxs-lookup"><span data-stu-id="5615d-128">Remarks</span></span>  
 <span data-ttu-id="5615d-129">Dado que el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye el código de SchemaValidator, puede agregar lógica a la utilidad.</span><span class="sxs-lookup"><span data-stu-id="5615d-129">Because the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes the SchemaValidator code, you can add logic to the utility.</span></span> <span data-ttu-id="5615d-130">Por ejemplo, puede realizar una utilidad de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5615d-130">For example, you can make it a command-line utility.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5615d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="5615d-131">See Also</span></span>  
 [<span data-ttu-id="5615d-132">Utilidades</span><span class="sxs-lookup"><span data-stu-id="5615d-132">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
