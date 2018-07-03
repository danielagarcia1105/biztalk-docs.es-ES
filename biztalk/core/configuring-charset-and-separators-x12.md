---
title: Configuración de juego de caracteres y separadores (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9615e3cdcf46872ff2d07ecdff4ea7288f09f94f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976693"
---
# <a name="configuring-charset-and-separators-x12"></a><span data-ttu-id="4133c-102">Configuración de juego de caracteres y separadores (X12)</span><span class="sxs-lookup"><span data-stu-id="4133c-102">Configuring Charset and Separators (X12)</span></span>
<span data-ttu-id="4133c-103">En el acuerdo de socios comerciales, puede especificar el juego de caracteres que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para validar las propiedades de entidad al crear el sobre para un mensaje X12 saliente.</span><span class="sxs-lookup"><span data-stu-id="4133c-103">In the partner agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="4133c-104">También puede especificar los separadores y terminadores que se usarán para los segmentos del intercambio.</span><span class="sxs-lookup"><span data-stu-id="4133c-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4133c-105">La configuración descrita aquí también se aplica a los intercambios HIPAA.</span><span class="sxs-lookup"><span data-stu-id="4133c-105">The settings described here also apply to HIPAA interchanges.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="4133c-106">Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="4133c-106">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="4133c-107">**Elemento de datos**</span><span class="sxs-lookup"><span data-stu-id="4133c-107">**Data element**</span></span>  
>   -   <span data-ttu-id="4133c-108">**Separador de elementos de componente (ISA16)**</span><span class="sxs-lookup"><span data-stu-id="4133c-108">**Component element separator (ISA16)**</span></span>  
>   -   <span data-ttu-id="4133c-109">**Terminador de segmento**</span><span class="sxs-lookup"><span data-stu-id="4133c-109">**Segment terminator**</span></span>  
>   -   <span data-ttu-id="4133c-110">**Sufijo**</span><span class="sxs-lookup"><span data-stu-id="4133c-110">**Suffix**</span></span>  
>   -   <span data-ttu-id="4133c-111">**Reemplazar separadores de carga con**</span><span class="sxs-lookup"><span data-stu-id="4133c-111">**Replace separators in payload with**</span></span>  
> 
>   <span data-ttu-id="4133c-112">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="4133c-112">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="4133c-113">Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="4133c-113">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4133c-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4133c-114">Prerequisites</span></span>  
 <span data-ttu-id="4133c-115">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4133c-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="4133c-116">Para configurar el juego de caracteres y los separadores</span><span class="sxs-lookup"><span data-stu-id="4133c-116">To configure the character set and separators</span></span>  
  
1. <span data-ttu-id="4133c-117">Crear un acuerdo de codificación, como se describe en X12 [configuración General de las opciones (X12)](../core/configuring-general-settings-x12.md).</span><span class="sxs-lookup"><span data-stu-id="4133c-117">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="4133c-118">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4133c-118">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="4133c-119">En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **juego de caracteres y separadores**.</span><span class="sxs-lookup"><span data-stu-id="4133c-119">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3. <span data-ttu-id="4133c-120">Desde el **juego de caracteres que se usará** lista desplegable, seleccione el X12 juego de caracteres que se usa para validar las propiedades que especifique para el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="4133c-120">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4133c-121"> solo usa esta configuración para validar los valores especificados para las propiedades de contrato relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4133c-121"> only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="4133c-122">La canalización de recepción o la de envío hará caso omiso de esta propiedad de juego de caracteres al realizar el procesamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4133c-122">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4. <span data-ttu-id="4133c-123">Para **elemento de datos**, especifique un único carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para separar elementos de datos compuestos que consta de dos o más elementos de datos simples y elementos de datos simples que no forman parte de un elemento compuesto.</span><span class="sxs-lookup"><span data-stu-id="4133c-123">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="4133c-124">Seleccione **Char** para un elemento de datos de caracteres o **Hex** para un elemento de datos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="4133c-124">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="4133c-125">El carácter que escriba cambiará automáticamente al cambiar el formato de **Char** a **Hex** o viceversa.</span><span class="sxs-lookup"><span data-stu-id="4133c-125">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5. <span data-ttu-id="4133c-126">Para **separador de elementos de componente (ISA16)**, especifique un único carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para separar elementos de datos simples dentro de los elementos de datos compuestos.</span><span class="sxs-lookup"><span data-stu-id="4133c-126">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="4133c-127">Seleccione **Char** para un elemento de datos de caracteres o **Hex** para un elemento de datos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="4133c-127">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="4133c-128">El carácter que escriba cambiará automáticamente al cambiar el formato de **Char** a **Hex** o viceversa.</span><span class="sxs-lookup"><span data-stu-id="4133c-128">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6. <span data-ttu-id="4133c-129">Para **terminador de segmento**, escriba un único carácter para indicar el final de un segmento EDI.</span><span class="sxs-lookup"><span data-stu-id="4133c-129">For **Segment terminator**, enter a single character to indicate the end of an EDI segment.</span></span> <span data-ttu-id="4133c-130">Seleccione **Char** para un elemento de datos de caracteres o **Hex** para un elemento de datos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="4133c-130">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span>  
  
    <span data-ttu-id="4133c-131">Si el tipo es **Char**, el valor predeterminado es **~**.</span><span class="sxs-lookup"><span data-stu-id="4133c-131">If the type is **Char**, the default value is **~**.</span></span>  
  
    <span data-ttu-id="4133c-132">Si el tipo es **Hex**, el valor predeterminado es **7E**.</span><span class="sxs-lookup"><span data-stu-id="4133c-132">If the type is **Hex**, the default value is **7E**.</span></span>  
  
    <span data-ttu-id="4133c-133">Este elemento de datos es necesario.</span><span class="sxs-lookup"><span data-stu-id="4133c-133">This data element is required.</span></span>  
  
    <span data-ttu-id="4133c-134">Este elemento está limitado a los valores del juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="4133c-134">This element is limited to the values in the ASCII character set.</span></span> <span data-ttu-id="4133c-135">Esta propiedad no se valida con respecto al juego de caracteres X12 definido en la página General.</span><span class="sxs-lookup"><span data-stu-id="4133c-135">This property is not validated against the X12 character set defined in the General page.</span></span>  
  
    <span data-ttu-id="4133c-136">El carácter que escriba cambiará automáticamente al cambiar el formato de **Char** a **Hex** o viceversa.</span><span class="sxs-lookup"><span data-stu-id="4133c-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7. <span data-ttu-id="4133c-137">Para **sufijo**, seleccione el carácter que se va a usar **con** el valor de terminador de segmento.</span><span class="sxs-lookup"><span data-stu-id="4133c-137">For **Suffix**, select the character to use **with** the Segment Terminator value.</span></span> <span data-ttu-id="4133c-138">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="4133c-138">Options include:</span></span>  
  
   - <span data-ttu-id="4133c-139">**Ninguno**: predeterminado</span><span class="sxs-lookup"><span data-stu-id="4133c-139">**None**: Default</span></span>  
  
   - <span data-ttu-id="4133c-140">**CR**: retorno de carro</span><span class="sxs-lookup"><span data-stu-id="4133c-140">**CR**: Carriage Return</span></span>  
  
   - <span data-ttu-id="4133c-141">**LF**: avance de línea</span><span class="sxs-lookup"><span data-stu-id="4133c-141">**LF**: Line Feed</span></span>  
  
   - <span data-ttu-id="4133c-142">**CR LF**: / línea de retorno de carro, avance</span><span class="sxs-lookup"><span data-stu-id="4133c-142">**CR LF**: Carriage Return/Line Feed</span></span>  
  
     <span data-ttu-id="4133c-143">Entre las combinaciones de Terminador de segmento y Sufijo se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4133c-143">The Segment Terminator and Suffix combinations include the following:</span></span>  
  
   - <span data-ttu-id="4133c-144">**Cualquier** terminador de segmento + **ninguno** sufijo</span><span class="sxs-lookup"><span data-stu-id="4133c-144">**Any** Segment Terminator + **None** Suffix</span></span>  
  
   - <span data-ttu-id="4133c-145">**Cualquier** terminador de segmento + **CR** sufijo</span><span class="sxs-lookup"><span data-stu-id="4133c-145">**Any** Segment Terminator + **CR** Suffix</span></span>  
  
   - <span data-ttu-id="4133c-146">**Cualquier** terminador de segmento + **CR LF** sufijo</span><span class="sxs-lookup"><span data-stu-id="4133c-146">**Any** Segment Terminator + **CR LF** Suffix</span></span>  
  
   - <span data-ttu-id="4133c-147">**D. (Hex)** terminador de segmento + **ninguno** sufijo: esta combinación se comporta como si está en blanco terminador de segmento y sufijo se hubiera definido como CR.</span><span class="sxs-lookup"><span data-stu-id="4133c-147">**D (Hex)** Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to CR.</span></span>  
  
   - <span data-ttu-id="4133c-148">Un terminador de segmento (Hex) + **ninguno** sufijo: esta combinación se comporta como si está en blanco terminador de segmento y sufijo se hubiera definido como LF.</span><span class="sxs-lookup"><span data-stu-id="4133c-148">A (Hex) Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to LF.</span></span>  
  
   - <span data-ttu-id="4133c-149">**D. (Hex)** terminador de segmento + **LF** sufijo: esta combinación se comporta como si el terminador de segmento es CR y el sufijo se hubiera definido como LF.</span><span class="sxs-lookup"><span data-stu-id="4133c-149">**D (Hex)** Segment Terminator + **LF** Suffix: This combination behaves as if Segment Terminator is CR and Suffix is set to LF.</span></span>  
  
8. <span data-ttu-id="4133c-150">Compruebe si los datos de carga contienen caracteres que también se usan como datos, segmentos o separadores de componentes, **reemplazar separadores de carga con** y especificar un carácter de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="4133c-150">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="4133c-151">Al generar el mensaje X12 de salida, todas las instancias de caracteres de separador en los datos de carga se sustituirán por el carácter especificado.</span><span class="sxs-lookup"><span data-stu-id="4133c-151">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="4133c-152">Seleccione **Char** para un elemento de datos de caracteres o **Hex** para un elemento de datos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="4133c-152">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="4133c-153">El carácter que escriba cambiará automáticamente al cambiar el formato de **Char** a **Hex** o viceversa.</span><span class="sxs-lookup"><span data-stu-id="4133c-153">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="4133c-154">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4133c-154">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4133c-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="4133c-155">See Also</span></span>  
 [<span data-ttu-id="4133c-156">Configuración de las opciones de intercambio (X12)</span><span class="sxs-lookup"><span data-stu-id="4133c-156">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)