---
title: Validar una instancia (EDI) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0fe4e87-5ab4-41e4-8ceb-8f6cf40cae0b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cceea8afe67f7e69b3ee842198d9a5373a972d04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="validating-an-instance-edi"></a><span data-ttu-id="3d629-102">Validar instancias (EDI)</span><span class="sxs-lookup"><span data-stu-id="3d629-102">Validating an Instance (EDI)</span></span>
<span data-ttu-id="3d629-103">Las instancias pueden validarse con respecto a su esquema EDI en el tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="3d629-103">You can validate an instance against its EDI schema at design time.</span></span> <span data-ttu-id="3d629-104">Para ello, se usan las extensiones de la herramienta XML para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d629-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="3d629-105">La instancia que valide puede ser un único conjunto de transacciones (sin intercambio ni encabezados de grupo), un intercambio con un único conjunto de transacciones (con intercambio y encabezados de grupo) o un intercambio procesado por lotes completo con varios conjuntos de transacciones (con intercambio y encabezados de grupo).</span><span class="sxs-lookup"><span data-stu-id="3d629-105">The instance that you validate can be a single transaction set (without interchange and group headers), an interchange with a single transaction set (with interchange and group headers), or a complete batched interchange with multiple transaction sets (with interchange and group headers).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d629-106">Validación de un intercambio conservado XML no es compatible.</span><span class="sxs-lookup"><span data-stu-id="3d629-106">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="3d629-107">Sin embargo, la validación de un intercambio conservado EDI sí es compatible.</span><span class="sxs-lookup"><span data-stu-id="3d629-107">However, validation of an EDI preserved interchange is supported.</span></span>  
  
 <span data-ttu-id="3d629-108">La operación de validar instancia realiza tanto la validación EDI como la XSD.</span><span class="sxs-lookup"><span data-stu-id="3d629-108">The validate-instance operation performs both EDI and XSD validation.</span></span>  
  
 <span data-ttu-id="3d629-109">Cuando se valida una instancia, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] muestra un cuadro de diálogo en el que se especifica la configuración que se va a validar en ella, incluidos los separadores y el identificador de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="3d629-109">When you validate an instance, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] displays a dialog box in which you specify the configuration to be validated in that instance, including separators and the syntax identifier.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d629-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3d629-110">Prerequisites</span></span>  
 <span data-ttu-id="3d629-111">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d629-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-an-instance-against-its-schema"></a><span data-ttu-id="3d629-112">Para validar una instancia con respecto a su esquema</span><span class="sxs-lookup"><span data-stu-id="3d629-112">To validate an instance against its schema</span></span>  
  
1.  <span data-ttu-id="3d629-113">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto.</span><span class="sxs-lookup"><span data-stu-id="3d629-113">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span>  
  
2.  <span data-ttu-id="3d629-114">En el Explorador de soluciones, agregue al proyecto todos los esquemas necesarios para la instancia del mensaje.</span><span class="sxs-lookup"><span data-stu-id="3d629-114">In Solution Explorer, add to the project all schemas required for the message instance.</span></span>  
  
    1.  <span data-ttu-id="3d629-115">Si valida un único conjunto de transacciones sin intercambio ni encabezados de grupo, agregue el esquema de documento para ese conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="3d629-115">If you are validating a single transaction set without interchange and group headers, add the document schema for that transaction set.</span></span>  
  
    2.  <span data-ttu-id="3d629-116">Si valida un intercambio con un único conjunto de transacciones, agregue al proyecto el esquema para la transacción y el esquema de lote para el tipo de codificación que se usa en el mensaje (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span><span class="sxs-lookup"><span data-stu-id="3d629-116">If you are validating an interchange with a single transaction set, add to the project the schema for the transaction and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3d629-117">El esquema de lote es necesario para validar el sobre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="3d629-117">The batch schema is required to validate the envelope of the instance.</span></span> <span data-ttu-id="3d629-118">Si usara únicamente el esquema de mensaje, el sobre no se validaría.</span><span class="sxs-lookup"><span data-stu-id="3d629-118">If you were to use only the message schema, the envelope would not be validated.</span></span>  
  
    3.  <span data-ttu-id="3d629-119">Si va a validar un intercambio por lotes con varios conjuntos de transacciones, agregue al proyecto los esquemas para cada grupo de conjuntos de transacciones en la instancia de mensaje y el esquema de lote para el tipo de codificación que se usa en el mensaje (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span><span class="sxs-lookup"><span data-stu-id="3d629-119">If you are validating a batched interchange with multiple transaction sets, add to the project the schemas for each transaction set group in the message instance, and the batch schema for the type of encoding used for the message (either Edifact_BatchSchema.xsd or X12_BatchSchema.xsd in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3d629-120">Si ha personalizado el esquema de servicios, tendrá que incluir el esquema de servicio personalizado en el proyecto de BizTalk, además de los esquemas de documento (conjunto de transacciones) y, si es necesario, el esquema por lotes.</span><span class="sxs-lookup"><span data-stu-id="3d629-120">If you have customized the service schema, you will have to include the custom service schema in the BizTalk project, in addition to the document (transaction set) schema(s) and if necessary, the batch schema.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3d629-121">No tiene que generar el proyecto para validar una instancia.</span><span class="sxs-lookup"><span data-stu-id="3d629-121">You do not have to build the project to validate an instance.</span></span>  
  
3.  <span data-ttu-id="3d629-122">Para que la página de propiedades del esquema aparezca en el Explorador de soluciones, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d629-122">Display the property page for the schema in Solution Explorer, as follows:</span></span>  
  
    1.  <span data-ttu-id="3d629-123">Si va a validar un único conjunto de transacciones, haga clic en el esquema de documento para ese conjunto de transacciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3d629-123">If you are validating a single transaction set, right-click the document schema for that transaction set, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="3d629-124">Si va a validar un intercambio con un único conjunto de transacciones o un intercambio por lotes con varios conjuntos de transacciones, haga clic en el esquema por lotes (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd esquema) y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3d629-124">If you are validating an interchange with a single transaction set or a batched interchange with multiple transaction sets, right-click the batch schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd schema), and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3d629-125">En la ventana Propiedades para el esquema, para **nombre de archivo de instancia de entrada** escriba el nombre y la ruta de acceso de la instancia de mensaje que se desea validar, o busque el archivo, selecciónelo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3d629-125">In Properties window for the schema, for **Input Instance Filename** enter the name and path of the message instance that you want to validate, or browse to the file, select it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="3d629-126">Para **valide el tipo de entrada de instancia**, escriba el tipo de archivo que va a validar: **nativo** para los archivos EDI o **XML** para un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="3d629-126">For **Validate Instance Input Type**, enter the type of the file to be validate: **Native** for a EDI file or **XML** for an XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d629-127">Validación de un intercambio conservado XML no es compatible.</span><span class="sxs-lookup"><span data-stu-id="3d629-127">Validation of an XML preserved interchange is not supported.</span></span> <span data-ttu-id="3d629-128">Si selecciona XML para el **valide el tipo de entrada de instancia** propiedad cuando se valida un intercambio conservado, se producirá un error en la operación y se devolverá nada.</span><span class="sxs-lookup"><span data-stu-id="3d629-128">If you select XML for the **Validate Instance Input Type** property when validating a preserved interchange, the operation will fail and nothing will be returned.</span></span> <span data-ttu-id="3d629-129">Sin embargo, si selecciona **nativo** para el **valide el tipo de entrada de instancia** al validar un intercambio conservado, la operación se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d629-129">However, if you select **Native** for the **Validate Instance Input Type** when validating a preserved interchange, the operation will succeed.</span></span>  
  
6.  <span data-ttu-id="3d629-130">Haga clic en el esquema de mensaje (Edifact_BatchSchema.xsd o X12_BatchSchema.xsd si va a validar un intercambio con un único conjunto de transacciones o un intercambio por lotes) y, a continuación, haga clic en **Validar instancia**.</span><span class="sxs-lookup"><span data-stu-id="3d629-130">Right-click the message schema (Edifact_BatchSchema.xsd or X12_BatchSchema.xsd if validating an interchange with a single transaction set or a batched interchange) and then click **Validate Instance**.</span></span>  
  
7.  <span data-ttu-id="3d629-131">En el **propiedades de la instancia de EDI** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d629-131">In the **EDI Instance Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="3d629-132">Si la instancia debe utilizar un separador de repeticiones, seleccione **separador de repeticiones**.</span><span class="sxs-lookup"><span data-stu-id="3d629-132">If your instance should use a repetition separator, select **Repetition separator**.</span></span>  
  
    2.  <span data-ttu-id="3d629-133">Si la instancia debe utilizar delimitadores finales, seleccione **Sí** para **usar delimitadores finales**.</span><span class="sxs-lookup"><span data-stu-id="3d629-133">If your instance should use trailing delimiters, select **Yes** for **Use trailing delimiters**.</span></span>  
  
    3.  <span data-ttu-id="3d629-134">Si la instancia debe utilizar un conjunto distinto de caracteres **básica**, seleccione **extendido** o **Unicode** en **identificador de sintaxis**.</span><span class="sxs-lookup"><span data-stu-id="3d629-134">If your instance should use a character set other than **Basic**, select **Extended** or **Unicode** in **Syntax identifier**.</span></span>  
  
    4.  <span data-ttu-id="3d629-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3d629-135">Click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3d629-136">El **propiedades de la instancia de EDI** cuadro de diálogo puede aparecer una segunda vez después de que haya hecho clic **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3d629-136">The **EDI Instance Properties** dialog box might appear a second time after you have clicked **OK**.</span></span> <span data-ttu-id="3d629-137">Si es así, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="3d629-137">If so, click **OK** again.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3d629-138">El **propiedades de la instancia de EDI** cuadro de diálogo se llenará con los mismos valores usados en la última operación de validar instancia que se ha ejecutado para el mismo usuario ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3d629-138">The **EDI Instance Properties** dialog box will be populated with the same values used in the last validate-instance operation that was run for the same logged-in user.</span></span>  
  
8.  <span data-ttu-id="3d629-139">Compruebe que hay un mensaje en el **salida** ventana que indica que la operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d629-139">Verify that there is a message in the **Output** window indicating that the operation succeeded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d629-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d629-140">See Also</span></span>  
 <span data-ttu-id="3d629-141">[Uso de herramientas XML en tiempo de diseño](../core/using-design-time-xml-tools.md) </span><span class="sxs-lookup"><span data-stu-id="3d629-141">[Using Design-Time XML Tools](../core/using-design-time-xml-tools.md) </span></span>  
 [<span data-ttu-id="3d629-142">Generar una instancia (EDI)</span><span class="sxs-lookup"><span data-stu-id="3d629-142">Generating an Instance (EDI)</span></span>](../core/generating-an-instance-edi.md)