---
title: "Configuración de las propiedades de sobres de reserva (configuración de intercambio de X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e9b05ea-2a0f-42d6-adc2-c1f1f2b7a993
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a2b0c43a43f5b003015378ecc52c05405877c5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-x12-interchange-settings"></a><span data-ttu-id="9df6f-102">Configuración de propiedades de sobre de reserva (configuración de intercambio X12)</span><span class="sxs-lookup"><span data-stu-id="9df6f-102">Configuring Fallback Envelope Properties (X12-Interchange Settings)</span></span>
<span data-ttu-id="9df6f-103">La configuración de generación de sobres de intercambio X12 define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera el sobre de un intercambio con codificación X12 que va a enviarse a la entidad de recepción.</span><span class="sxs-lookup"><span data-stu-id="9df6f-103">X12 interchange envelope generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the envelope of an X12-encoded interchange to be sent to the receiving party.</span></span> <span data-ttu-id="9df6f-104">En este acuerdo de reserva, defina cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera el segmento ISA para un intercambio con codificación X12 que envía a la entidad.</span><span class="sxs-lookup"><span data-stu-id="9df6f-104">In this fallback agreement, you define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the ISA segment for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="9df6f-105">Un segmento ISA es el encabezado de control de intercambio para un intercambio con codificación X12.</span><span class="sxs-lookup"><span data-stu-id="9df6f-105">An ISA segment is the interchange control header for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9df6f-106">Para el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la longitud de los campos ISA alfanuméricos es fija.</span><span class="sxs-lookup"><span data-stu-id="9df6f-106">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime, the length of alphanumeric ISA fields is fixed.</span></span> <span data-ttu-id="9df6f-107">Sin embargo, para el [!INCLUDE[TPM](../includes/tpm-md.md)] interfaz de usuario, puede escribir un único carácter de un campo ISA alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="9df6f-107">However, for the [!INCLUDE[TPM](../includes/tpm-md.md)] user interface, you may enter a single character for an alphanumeric ISA field.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9df6f-108">rellenará estos campos con caracteres de espacio finales para garantizar el cumplimiento con los requisitos estándar.</span><span class="sxs-lookup"><span data-stu-id="9df6f-108"> will pad these fields with trailing space characters to ensure compliance with standards requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9df6f-109">La configuración descrita aquí también se aplica a la generación de sobres de intercambio HIPAA.</span><span class="sxs-lookup"><span data-stu-id="9df6f-109">The settings described here also apply to HIPAA interchange envelope generation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9df6f-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9df6f-110">Prerequisites</span></span>  
 <span data-ttu-id="9df6f-111">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9df6f-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-envelope"></a><span data-ttu-id="9df6f-112">Para definir el sobre</span><span class="sxs-lookup"><span data-stu-id="9df6f-112">To define the envelope</span></span>  
  
1.  <span data-ttu-id="9df6f-113">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="9df6f-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="9df6f-114">En el **X12 configuración de reserva** cuadro de diálogo la **X12 páginas del acuerdo** , bajo la **configuración de intercambio** sección, haga clic en **sobres**.</span><span class="sxs-lookup"><span data-stu-id="9df6f-114">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="9df6f-115">En **uso de ISA11**, mantener **identificador estándar** seleccionado para especificar un identificador estándar en lugar de un separador de repeticiones y, a continuación, seleccione un valor para el identificador estándar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9df6f-115">Under **ISA11 usage**, keep **Standard identifier** selected to specify a standard identifier instead of a repetition separator, and then select a value for the standard identifier from the drop-down list.</span></span> <span data-ttu-id="9df6f-116">Seleccione **separador de repeticiones** para especificar un separador de repeticiones en lugar de un identificador estándar y, a continuación, escriba un único carácter como separador de repeticiones.</span><span class="sxs-lookup"><span data-stu-id="9df6f-116">Select **Repetition separator** to specify a repetition separator instead of a standard identifier, and then enter a single character for the repetition separator.</span></span> <span data-ttu-id="9df6f-117">El separador de repeticiones, que se usa para separar segmentos que se repiten en un conjunto de transacciones, está limitado a los valores del juego de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="9df6f-117">The repetition separator, which is used to separate segments that repeat within a transaction set, is limited to the values in the ASCII character set.</span></span>  
  
4.  <span data-ttu-id="9df6f-118">Para **controlar el número de versión (ISA12)**, seleccione la versión de la X12 estándar que va a usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para generar un intercambio saliente.</span><span class="sxs-lookup"><span data-stu-id="9df6f-118">For **Control version number (ISA12)**, select the version of the X12 standard to be used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for generating an outgoing interchange.</span></span>  
  
5.  <span data-ttu-id="9df6f-119">Para **indicador de uso (ISA15)**, seleccione esta opción para indicar si un intercambio generado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es información, datos de producción o datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9df6f-119">For **Usage indicator (ISA15)**, select to indicate whether an interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is information, production data, or test data.</span></span>  
  
6.  <span data-ttu-id="9df6f-120">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9df6f-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df6f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9df6f-121">See Also</span></span>  
 [<span data-ttu-id="9df6f-122">Configuración de X12 propiedades de acuerdo de reserva para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="9df6f-122">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)