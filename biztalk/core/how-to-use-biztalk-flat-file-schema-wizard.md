---
title: Cómo usar el Asistente para esquemas de archivo sin formato de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7cb8b18-266d-422e-bdb8-1efefb6b4c8e
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff7d87959bd39b9040a495022c2b7bf352954848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258300"
---
# <a name="how-to-use-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-102">Cómo utilizar el Asistente para esquemas de archivo sin formato de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cabd9-102">How to Use BizTalk Flat File Schema Wizard</span></span>
<span data-ttu-id="cabd9-103">En versiones anteriores de BizTalk Server había que agregar manualmente las anotaciones en los esquemas del lenguaje de definición de esquemas XML (XSD) en el Editor de esquema de BizTalk para que los esquemas fueran comprensibles para los componentes de canalización de archivos sin formato, como el Desensamblador de archivo sin formato y el Ensamblador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="cabd9-103">In previous releases of BizTalk Server, you had to manually add the annotations to XML Schema Definition language (XSD) schemas in the BizTalk Schema Editor to make these schemas understandable to Flat File Pipeline components, such as Flat File Disassembler and Flat File Assembler.</span></span> <span data-ttu-id="cabd9-104">Puede seguir haciéndolo con el editor de esquemas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cabd9-104">You can still do this using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Schema Editor.</span></span> <span data-ttu-id="cabd9-105">Para reducir el número de pasos manuales, así como el tiempo necesario para crear soluciones, utilice el Asistente para esquemas de archivos sin formato de BizTalk, que ofrece las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cabd9-105">To reduce the number of manual steps and time needed to create solutions, you use the BizTalk Flat File Schema Wizard, which provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="cabd9-106">Utiliza instancias de archivo sin formato real como entrada.</span><span class="sxs-lookup"><span data-stu-id="cabd9-106">Uses real flat file instances as input.</span></span>  
  
-   <span data-ttu-id="cabd9-107">Incluye una superficie de diseño visual para trabajar con esquemas de archivo sin formato delimitado y posicional.</span><span class="sxs-lookup"><span data-stu-id="cabd9-107">Includes a visual design surface for working with delimited and positional flat file schemas.</span></span>  
  
-   <span data-ttu-id="cabd9-108">Utiliza un proceso reentrante basado en asistentes para agregar elementos al esquema y definir anotaciones relacionadas con los archivos sin formato de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="cabd9-108">Uses a re-entrant wizard-based process for adding elements to the schema and defining flat file related annotations interactively.</span></span>  
  
-   <span data-ttu-id="cabd9-109">Proporciona compatibilidad para los identificadores de etiquetas y los delimitadores hexadecimales y de caracteres.</span><span class="sxs-lookup"><span data-stu-id="cabd9-109">Provides support for tag identifiers and character and hexadecimal delimiters.</span></span>  
  
-   <span data-ttu-id="cabd9-110">Determina automáticamente los desplazamientos de identificadores de etiquetas y el orden de delimitación del elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="cabd9-110">Automatically determines tag identifier offsets and child delimiting order.</span></span>  
  
-   <span data-ttu-id="cabd9-111">Ofrece funciones de vista previa para el formato del archivo.</span><span class="sxs-lookup"><span data-stu-id="cabd9-111">Provides preview capabilities for the file format.</span></span>  
  
-   <span data-ttu-id="cabd9-112">Permite seleccionar los datos secundarios dentro de la instancia de intercambio que se va a utilizar para definir los esquemas de archivos sin formato.</span><span class="sxs-lookup"><span data-stu-id="cabd9-112">Enables you to select preferred sub-data within the interchange instance to use to define the flat file schemas.</span></span>  
  
## <a name="how-to-start-the-biztalk-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-113">Cómo iniciar el Asistente para esquemas de archivos sin formato de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cabd9-113">How to Start the BizTalk Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cabd9-114">Puede iniciar el asistente desde el Explorador de soluciones de Microsoft Visual Studio o desde el Editor de esquema de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cabd9-114">You can start the wizard from either the Microsoft Visual Studio Solution Explorer or from the BizTalk Schema Editor.</span></span>  
  
#### <a name="to-start-the-wizard-from-solution-explorer"></a><span data-ttu-id="cabd9-115">Para iniciar el asistente desde el Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="cabd9-115">To start the wizard from Solution Explorer</span></span>  
  
1.  <span data-ttu-id="cabd9-116">En Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-116">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="cabd9-117">Para agregar el nuevo esquema de archivo sin formato, haga clic en el proyecto de BizTalk y seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-117">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span>  
  
3.  <span data-ttu-id="cabd9-118">Haga clic en **nuevo elemento.**</span><span class="sxs-lookup"><span data-stu-id="cabd9-118">Click **New Item.**</span></span>  
  
     <span data-ttu-id="cabd9-119">![Menú Explorador de soluciones](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span><span class="sxs-lookup"><span data-stu-id="cabd9-119">![Solution Explorer menu](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")</span></span>  
  
4.  <span data-ttu-id="cabd9-120">En el **Agregar nuevo elemento** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cabd9-120">In the **Add New Item** window, do the following:</span></span>  
  
    1.  <span data-ttu-id="cabd9-121">En el **categorías** sección, seleccione **archivos de esquema**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-121">In the **Categories** section, select **Schema Files**.</span></span>  
  
    2.  <span data-ttu-id="cabd9-122">En el **plantillas** sección, seleccione **Asistente para esquemas de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-122">In the **Templates** section, select **Flat File Schema Wizard**.</span></span>  
  
    3.  <span data-ttu-id="cabd9-123">En el **nombre** cuadro de texto, escriba un nombre para el nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="cabd9-123">In the **Name** text box, type a name for the new schema.</span></span>  
  
    4.  <span data-ttu-id="cabd9-124">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-124">Click **Add**.</span></span>  
  
         <span data-ttu-id="cabd9-125">Se abre el Asistente para esquema de archivo sin formato de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cabd9-125">The BizTalk Flat File Schema Wizard opens.</span></span>  
  
#### <a name="to-start-the-wizard-from-the-schema-editor"></a><span data-ttu-id="cabd9-126">Para iniciar el asistente desde el Editor de esquema</span><span class="sxs-lookup"><span data-stu-id="cabd9-126">To start the Wizard from the Schema Editor</span></span>  
  
1.  <span data-ttu-id="cabd9-127">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra el **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-127">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="cabd9-128">Para agregar el nuevo esquema de archivo sin formato, haga clic en el proyecto de BizTalk y seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-128">To add the new flat-file schema, right-click the BizTalk project, and select **Add**.</span></span> <span data-ttu-id="cabd9-129">Seleccione **nuevo elemento** y haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-129">Select **New Item** and click **New Item**.</span></span>  
  
3.  <span data-ttu-id="cabd9-130">En el **Agregar nuevo elemento** ventana, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cabd9-130">In the **Add New Item** window, do the following:</span></span>  
  
    1.  <span data-ttu-id="cabd9-131">En el **categorías** sección, seleccione **archivos de esquema**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-131">In the **Categories** section, select **Schema Files**.</span></span>  
  
    2.  <span data-ttu-id="cabd9-132">En el **plantillas** sección, seleccione **esquema de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-132">In the **Templates** section, select **Flat File Schema**.</span></span>  
  
    3.  <span data-ttu-id="cabd9-133">En el **nombre** cuadro de texto, escriba un nombre para el nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="cabd9-133">In the **Name** text box, type a name for the new schema.</span></span>  
  
    4.  <span data-ttu-id="cabd9-134">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-134">Click **Add**.</span></span>  
  
    5.  <span data-ttu-id="cabd9-135">Haga clic en **raíz** y seleccione **definir registro desde instancia de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-135">Right-click **Root** and select **Define Record from Flat File Instance**.</span></span>  
  
         <span data-ttu-id="cabd9-136">Ahora se inicia el Asistente para esquemas de archivos sin formato de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cabd9-136">The BizTalk Flat File Schema Wizard now starts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cabd9-137">Si tiene un esquema en funcionamiento abierto en el Editor de esquemas, todo lo que necesita hacer es haga clic en el nodo seleccionado y, a continuación, seleccione **definir registro desde instancia de archivo sin formato**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-137">If you have a working schema opened in the Schema Editor, all you need to do is right-click the selected node and then select **Define Record from Flat File Instance**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cabd9-138">El **definir registro desde instancia de archivo sin formato** opción está habilitada si el nodo seleccionado es un registro sin elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="cabd9-138">The **Define Record from Flat File Instance** option is enabled if the selected node is a record without child elements.</span></span> <span data-ttu-id="cabd9-139">Si el nodo seleccionado tiene elementos secundarios, el asistente elimina todos los elementos secundarios actuales y genera los nuevos.</span><span class="sxs-lookup"><span data-stu-id="cabd9-139">If the selected node has child elements, the wizard deletes all current child elements and generates the new ones.</span></span> <span data-ttu-id="cabd9-140">El asistente le solicita que confirme la eliminación de los elementos secundarios existentes.</span><span class="sxs-lookup"><span data-stu-id="cabd9-140">The wizard prompts you to confirm before deleting the existing child elements.</span></span>  
  
## <a name="considerations-for-using-the-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-141">Consideraciones sobre el uso del Asistente para esquemas de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="cabd9-141">Considerations for Using the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cabd9-142">En esta sección se describen los aspectos que debería tener en cuenta al trabajar con el Asistente para esquemas de archivos sin formato de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="cabd9-142">This section describes issues you should consider when working with the BizTalk Flat File Schema Wizard.</span></span>  
  
### <a name="working-with-multibyte-character-set-mbcs"></a><span data-ttu-id="cabd9-143">Trabajar con juegos de caracteres multibyte (MBCS)</span><span class="sxs-lookup"><span data-stu-id="cabd9-143">Working with Multibyte Character Set (MBCS)</span></span>  
 <span data-ttu-id="cabd9-144">De forma predeterminada, el **contar posiciones en bytes** casilla de verificación está desactivada en la pantalla de información de esquema de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="cabd9-144">By default, the **Count positions in bytes** check box is unchecked on the Flat File Schema Information screen.</span></span> <span data-ttu-id="cabd9-145">El asistente cuenta las posiciones por caracteres, lo que significa que si tiene caracteres MBCS en la instancia de archivo sin formato posicional, las posiciones no se contarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="cabd9-145">The wizard counts the positions by characters; which mean that if you have MBCS characters in your positional flat file instance, the positions are not counted correctly.</span></span> <span data-ttu-id="cabd9-146">Si selecciona el **contar posiciones en bytes** casilla de verificación, el asistente muestra caracteres MBCS con una indicación adicional de su longitud posicional.</span><span class="sxs-lookup"><span data-stu-id="cabd9-146">By selecting the **Count positions in bytes** check box, the wizard displays MBCS characters with an additional indication of their positional length.</span></span> <span data-ttu-id="cabd9-147">El carácter toma una posición en la pantalla y se rellena la longitud restante con símbolos de punto " •".</span><span class="sxs-lookup"><span data-stu-id="cabd9-147">The character takes one position on the display and the remaining length is filled out with dot symbols, “•”.</span></span> <span data-ttu-id="cabd9-148">El número de símbolos de punto rellenos dependerá de los archivos que se guardaran en el juego de caracteres de doble byte, formato Unicode o UTF-8.</span><span class="sxs-lookup"><span data-stu-id="cabd9-148">The number of dot symbols filled will be depending on the files that were saved in double byte character set (DBCS), Unicode or UTF-8 format.</span></span>  
  
### <a name="code-pages-supported-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-149">Páginas de códigos compatibles en el Asistente para esquemas de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="cabd9-149">Code Pages Supported in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cabd9-150">A continuación, se muestra una lista de las páginas de códigos compatibles del asistente:</span><span class="sxs-lookup"><span data-stu-id="cabd9-150">The following is a list of supported code pages for the wizard:</span></span>  
  
-   <span data-ttu-id="cabd9-151">Árabe (1256)</span><span class="sxs-lookup"><span data-stu-id="cabd9-151">Arabic (1256)</span></span>  
  
-   <span data-ttu-id="cabd9-152">ASCII (20127)</span><span class="sxs-lookup"><span data-stu-id="cabd9-152">ASCII (20127)</span></span>  
  
-   <span data-ttu-id="cabd9-153">Báltico (1257)</span><span class="sxs-lookup"><span data-stu-id="cabd9-153">Baltic (1257)</span></span>  
  
-   <span data-ttu-id="cabd9-154">Big-Endian-UTF16 (1201)</span><span class="sxs-lookup"><span data-stu-id="cabd9-154">Big-Endian-UTF16 (1201)</span></span>  
  
-   <span data-ttu-id="cabd9-155">Centro Europeo (1250)</span><span class="sxs-lookup"><span data-stu-id="cabd9-155">Central-European (1250)</span></span>  
  
-   <span data-ttu-id="cabd9-156">Cirílico (1251)</span><span class="sxs-lookup"><span data-stu-id="cabd9-156">Cyrillic (1251)</span></span>  
  
-   <span data-ttu-id="cabd9-157">Griego (1253)</span><span class="sxs-lookup"><span data-stu-id="cabd9-157">Greek (1253)</span></span>  
  
-   <span data-ttu-id="cabd9-158">Hebreo (1255)</span><span class="sxs-lookup"><span data-stu-id="cabd9-158">Hebrew (1255)</span></span>  
  
-   <span data-ttu-id="cabd9-159">Japonés Shift_JIS (932)</span><span class="sxs-lookup"><span data-stu-id="cabd9-159">Japanese-Shift-JIS (932)</span></span>  
  
-   <span data-ttu-id="cabd9-160">Coreano (949)</span><span class="sxs-lookup"><span data-stu-id="cabd9-160">Korean (949)</span></span>  
  
-   <span data-ttu-id="cabd9-161">Little-Endian-UTF16 (1200)</span><span class="sxs-lookup"><span data-stu-id="cabd9-161">Little-Endian-UTF16 (1200)</span></span>  
  
-   <span data-ttu-id="cabd9-162">Chino-simplificado-GBK (936)</span><span class="sxs-lookup"><span data-stu-id="cabd9-162">Simplified-Chinese-GBK (936)</span></span>  
  
-   <span data-ttu-id="cabd9-163">Chino-simplificado-GB18030 (54936)</span><span class="sxs-lookup"><span data-stu-id="cabd9-163">Simplified-Chinese-GB18030 (54936)</span></span>  
  
-   <span data-ttu-id="cabd9-164">Tailandés (874)</span><span class="sxs-lookup"><span data-stu-id="cabd9-164">Thai (874)</span></span>  
  
-   <span data-ttu-id="cabd9-165">Chino-tradicional-BIG5 (950)</span><span class="sxs-lookup"><span data-stu-id="cabd9-165">Traditional-Chinese-BIG5 (950)</span></span>  
  
-   <span data-ttu-id="cabd9-166">Turco (1254)</span><span class="sxs-lookup"><span data-stu-id="cabd9-166">Turkish (1254)</span></span>  
  
-   <span data-ttu-id="cabd9-167">UTF-7 (65000)</span><span class="sxs-lookup"><span data-stu-id="cabd9-167">UTF-7 (65000)</span></span>  
  
-   <span data-ttu-id="cabd9-168">UTF-8 (65001)</span><span class="sxs-lookup"><span data-stu-id="cabd9-168">UTF-8 (65001)</span></span>  
  
-   <span data-ttu-id="cabd9-169">Vietnamita (1258)</span><span class="sxs-lookup"><span data-stu-id="cabd9-169">Vietnamese (1258)</span></span>  
  
-   <span data-ttu-id="cabd9-170">Europeo occidental (1252)</span><span class="sxs-lookup"><span data-stu-id="cabd9-170">Western-European (1252)</span></span>  
  
### <a name="record-types-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-171">Tipos de registro del esquema Asistente de esquemas de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="cabd9-171">Record Types in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cabd9-172">Los archivos sin formato no pueden contener registros delimitados dentro de registros posicionales.</span><span class="sxs-lookup"><span data-stu-id="cabd9-172">Flat files cannot contain delimited records within positional records.</span></span> <span data-ttu-id="cabd9-173">Dado que el asistente es reentrante basado, los botones de opción que definen el tipo de la **por símbolo delimitador** y **por posiciones relativas** se habilitan o deshabilitan según el formato de los registros primarios para el elemento secundario que se define en el asistente.</span><span class="sxs-lookup"><span data-stu-id="cabd9-173">Because the wizard is re-entrant based, the radio buttons that define the type of the **By delimiter symbol** and **By relative positions** are enabled or disabled based on the format of the parent records for the child which you define in the wizard.</span></span> <span data-ttu-id="cabd9-174">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="cabd9-174">For example,</span></span>  
  
-   <span data-ttu-id="cabd9-175">Si se ejecuta el asistente en un elemento secundario de un registro delimitado, se seleccionan los dos botones de opción.</span><span class="sxs-lookup"><span data-stu-id="cabd9-175">If the wizard is run for a child of a delimited record, both radio buttons are selected.</span></span>  
  
-   <span data-ttu-id="cabd9-176">Si se ejecuta el Asistente en un elemento secundario de un registro posicional, el **por símbolo delimitador** botón de radio está desactivada.</span><span class="sxs-lookup"><span data-stu-id="cabd9-176">If the wizard is run for a child of a positional record, the **By delimiter symbol** radio button is cleared.</span></span>  
  
### <a name="delimiter-symbols-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-177">Símbolos delimitadores del Asistente de esquemas de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="cabd9-177">Delimiter Symbols in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cabd9-178">La lista desplegable de propiedades del delimitador secundario contiene los siguientes delimitadores comunes:</span><span class="sxs-lookup"><span data-stu-id="cabd9-178">The child delimiter property drop-down list contains with the following common delimiters:</span></span>  
  
-   <span data-ttu-id="cabd9-179">{CR}{LF}</span><span class="sxs-lookup"><span data-stu-id="cabd9-179">{CR}{LF}</span></span>  
  
-   <span data-ttu-id="cabd9-180">{CR}</span><span class="sxs-lookup"><span data-stu-id="cabd9-180">{CR}</span></span>  
  
-   <span data-ttu-id="cabd9-181">{LF}</span><span class="sxs-lookup"><span data-stu-id="cabd9-181">{LF}</span></span>  
  
-   <span data-ttu-id="cabd9-182">{TAB}</span><span class="sxs-lookup"><span data-stu-id="cabd9-182">{TAB}</span></span>  
  
-   <span data-ttu-id="cabd9-183">{SPACE}</span><span class="sxs-lookup"><span data-stu-id="cabd9-183">{SPACE}</span></span>  
  
-   <span data-ttu-id="cabd9-184">{0x1A}</span><span class="sxs-lookup"><span data-stu-id="cabd9-184">{0x1A}</span></span>  
  
-   <span data-ttu-id="cabd9-185">&#124;</span><span class="sxs-lookup"><span data-stu-id="cabd9-185">&#124;</span></span>  
  
-   <span data-ttu-id="cabd9-186">,</span><span class="sxs-lookup"><span data-stu-id="cabd9-186">,</span></span>  
  
-   <span data-ttu-id="cabd9-187">;</span><span class="sxs-lookup"><span data-stu-id="cabd9-187">;</span></span>  
  
 <span data-ttu-id="cabd9-188">El valor predeterminado de esta propiedad es {CR}{LF}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-188">The default value for this property is {CR}{LF}.</span></span> <span data-ttu-id="cabd9-189">La propiedad también es un cuadro de texto editable, por lo que puede especificar el delimitador secundario como una secuencia de caracteres o como valores hexadecimales de los caracteres.</span><span class="sxs-lookup"><span data-stu-id="cabd9-189">The property is also an editable text box, so that you can specify the child delimiter as a sequence of characters or as hexadecimal values of the characters.</span></span> <span data-ttu-id="cabd9-190">Un ejemplo del uso de caracteres del delimitador secundario sería "una" o "calle".</span><span class="sxs-lookup"><span data-stu-id="cabd9-190">An example of using characters for the child delimiter would be "a" or "street."</span></span> <span data-ttu-id="cabd9-191">Los delimitadores hexadecimales se especifican con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="cabd9-191">Hexadecimal delimiters are specified using the following format:</span></span>  
  
-   <span data-ttu-id="cabd9-192">{0xnnnn}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-192">{0xnnnn}.</span></span> <span data-ttu-id="cabd9-193">Por ejemplo, {0x0D} {0x0A}, {0 x 09} o {0 x 20}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-193">For example, {0x0D}{0x0A}, {0x09} or {0x20}.</span></span>  
  
 <span data-ttu-id="cabd9-194">Un ejemplo del uso de la secuencia de valores hexadecimales es {0x0D}{0x0A}, {0x09}{0x20}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-194">An example of using sequence of hexadecimal values is {0x0D}{0x0A}, {0x09}{0x20}.</span></span>  
  
 <span data-ttu-id="cabd9-195">Si utiliza los símbolos \\, {, o} como delimitador, debe colocar un símbolo de barra diagonal inversa adicional delante del símbolo delimitador, en caso contrario, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="cabd9-195">If you use the symbols \\, {, or } as the delimiter, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message.</span></span> <span data-ttu-id="cabd9-196">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="cabd9-196">For example,</span></span>  
  
-   <span data-ttu-id="cabd9-197">\\\\, \\{, o \\}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-197">\\\\, \\{, or \\}.</span></span>  
  
### <a name="relative-positions-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-198">Posiciones relativas en el Asistente de esquemas de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="cabd9-198">Relative Positions in the Flat File Schema Wizard</span></span>  
  
#### <a name="setting-position-markers"></a><span data-ttu-id="cabd9-199">Establecimiento de marcadores de posición</span><span class="sxs-lookup"><span data-stu-id="cabd9-199">Setting Position Markers</span></span>  
 <span data-ttu-id="cabd9-200">Use el botón primario del mouse para hacer clic en un marcador de posición en el cuadro de selección de posición para establecer la nueva línea del marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="cabd9-200">Use the left mouse button to click a position marker in the position selection box to set the new position marker line.</span></span> <span data-ttu-id="cabd9-201">El marcador de posición se representa como una línea continua.</span><span class="sxs-lookup"><span data-stu-id="cabd9-201">The position marker is represented as a solid line.</span></span> <span data-ttu-id="cabd9-202">De forma predeterminada, existe una línea de marcador de posición al principio del registro en la posición cero.</span><span class="sxs-lookup"><span data-stu-id="cabd9-202">By default, a position marker line exists at the beginning of the record at position zero.</span></span> <span data-ttu-id="cabd9-203">Para quitar una línea de marcador de posición existente, haga clic en ella con el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="cabd9-203">To remove an existing position marker line, use the left mouse button to click  it.</span></span>  
  
### <a name="escape-characters-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-204">Caracteres de escape del Asistente de esquemas de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="cabd9-204">Escape Characters in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cabd9-205">Un carácter de escape es un carácter individual que suprime cualquier significado especial que tenga el carácter que le sigue.</span><span class="sxs-lookup"><span data-stu-id="cabd9-205">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="cabd9-206">Para obtener más información, consulte [caracteres de Escape](../core/escape-characters.md) tema en [formas de interpretar los caracteres especiales como parte de un valor de campo](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span><span class="sxs-lookup"><span data-stu-id="cabd9-206">For more information, see [Escape Characters](../core/escape-characters.md) topic under [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span> <span data-ttu-id="cabd9-207">Utiliza la propiedad de carácter de escape en el asistente para determinar el carácter de escape que se va a utilizar al analizar la instancia de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="cabd9-207">You use the escape character property in the wizard to specify the escape character to use when parsing the flat file instance.</span></span> <span data-ttu-id="cabd9-208">El valor predeterminado es nulo, lo que significa que se utiliza el carácter de escape predeterminado definido en el nivel de esquema.</span><span class="sxs-lookup"><span data-stu-id="cabd9-208">The default is null, meaning that the default escape character defined at the schema level is used.</span></span>  
  
 <span data-ttu-id="cabd9-209">El carácter de escape se puede definir como un carácter o como un valor hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="cabd9-209">The escape character can be specified as a character or as a hexadecimal value.</span></span> <span data-ttu-id="cabd9-210">El valor hexadecimal se especifica con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="cabd9-210">The hexadecimal value is specified using the following format:</span></span>  
  
-   <span data-ttu-id="cabd9-211">{0xnnnn}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-211">{0xnnnn}.</span></span> <span data-ttu-id="cabd9-212">Por ejemplo: {0x0D}{0x0A}, {0x09} o {0x20}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-212">For example, {0x0D}{0x0A}, {0x09}, or {0x20}.</span></span>  
  
 <span data-ttu-id="cabd9-213">Si utiliza los símbolos \\, {, o} como carácter de escape, debe colocar un símbolo de barra diagonal inversa adicional delante del símbolo delimitador, en caso contrario, recibirá un mensaje de error, por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="cabd9-213">If you use the symbols \\, {, or } as the escape character, you must place an additional backslash symbol in front of the delimiter symbol, otherwise you will receive an error message For example,</span></span>  
  
-   <span data-ttu-id="cabd9-214">\\\\, \\{, \\}.</span><span class="sxs-lookup"><span data-stu-id="cabd9-214">\\\\, \\{, \\}.</span></span>  
  
### <a name="child-elements-in-the-flat-file-schema-wizard"></a><span data-ttu-id="cabd9-215">Elementos secundarios del Asistente para esquema de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="cabd9-215">Child Elements in the Flat File Schema Wizard</span></span>  
 <span data-ttu-id="cabd9-216">Cada elemento secundario contiene **nombre del elemento**, **tipo de elemento**, **tipo de datos** y **contenido**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-216">Each child element contains **Element Name**, **Element Type**, **Data Type** and **Content**.</span></span> <span data-ttu-id="cabd9-217">Usa el **nombre del elemento** cuadro de texto para escribir un nombre descriptivo para el nodo.</span><span class="sxs-lookup"><span data-stu-id="cabd9-217">You use the **Element Name** text box to type a meaningful name for the node.</span></span> <span data-ttu-id="cabd9-218">El **tipo de elemento** es una lista desplegable con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="cabd9-218">The **Element Type** is a drop-down list with the following values:</span></span>  
  
-   <span data-ttu-id="cabd9-219">**Elemento de campo**: Especifica que este nodo se creará en el esquema como un elemento.</span><span class="sxs-lookup"><span data-stu-id="cabd9-219">**Field element**: Specifies that this node will be created in the schema as an element.</span></span>  
  
-   <span data-ttu-id="cabd9-220">**Atributo de campo**: Especifica que este nodo se creará en el esquema como un atributo.</span><span class="sxs-lookup"><span data-stu-id="cabd9-220">**Field attribute**: Specifies that this node will be created in the schema as an attribute.</span></span>  
  
-   <span data-ttu-id="cabd9-221">**Registro**: Especifica que se creará un registro sin elementos secundarios en el esquema.</span><span class="sxs-lookup"><span data-stu-id="cabd9-221">**Record**: Specifies that a record without children will be created in the schema.</span></span>  
  
-   <span data-ttu-id="cabd9-222">**Repitiendo registro**: Especifica que se creará un registro sin elementos secundarios en el esquema y sus repeticiones máximas se establecen en **Unbounded**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-222">**Repeating record**: Specifies that a record without children will be created in the schema and its max occurrence is set to **Unbounded**.</span></span>  
  
-   <span data-ttu-id="cabd9-223">**Omitir**: nada se crearán en el esquema de este nodo.</span><span class="sxs-lookup"><span data-stu-id="cabd9-223">**Ignore**: Nothing will be created in the schema for this node.</span></span>  
  
 <span data-ttu-id="cabd9-224">De forma predeterminada, todos los elementos son de tipo **elemento de campo** y su tipo de datos es **cadena**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-224">By default all elements are of type **Field element** and their data type is **string**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cabd9-225">Un elemento secundario puede declararse como un **atributo de campo** sólo si no hay ningún elemento secundario antes de que se declaran como **campo elementos**, **registro** o  **Repitiendo registro**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-225">A child element can be declared as a **Field attribute** only if there are no children before it that are declared as **Field elements**, **Record** or **Repeating record**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cabd9-226">Verá una marca de exclamación delante de la **nodos secundarios** en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cabd9-226">You will see an exclamation mark in front of the **child nodes** in the following instances:</span></span>  
  
-   <span data-ttu-id="cabd9-227">El **atributo de campo** se define después **elemento de campo**, **registro,** o **repitiendo registro**.</span><span class="sxs-lookup"><span data-stu-id="cabd9-227">The **Field attribute** is defined after **Field element**, **Record,** or **Repeating record**.</span></span>  
  
-   <span data-ttu-id="cabd9-228">El elemento secundario no tiene nombre.</span><span class="sxs-lookup"><span data-stu-id="cabd9-228">The child element does not have a name.</span></span>  
  
-   <span data-ttu-id="cabd9-229">El elemento secundario tiene un nombre duplicado.</span><span class="sxs-lookup"><span data-stu-id="cabd9-229">The child element has a duplicate name.</span></span>  
  
-   <span data-ttu-id="cabd9-230">El tipo de datos seleccionado para el elemento secundario no resulta adecuado para el contenido.</span><span class="sxs-lookup"><span data-stu-id="cabd9-230">The selected data type for the child element is not suitable for the content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cabd9-231">Vea también</span><span class="sxs-lookup"><span data-stu-id="cabd9-231">See Also</span></span>  
 [<span data-ttu-id="cabd9-232">Tutorial de Asistente de esquema de archivo sin formato de BizTalk</span><span class="sxs-lookup"><span data-stu-id="cabd9-232">BizTalk Flat File Schema Wizard Walkthrough</span></span>](../core/biztalk-flat-file-schema-wizard-walkthrough.md)