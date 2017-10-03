---
title: "Asistente para la configuración de línea de comandos para el adaptador de MQSeries | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], Command-Line Configuration Wizard
- Command-Line Configuration Wizard
- MQSeries adapters, Command-Line Configuration Wizard
ms.assetid: cab905d1-fe19-4d6a-be1b-f561e133e1d2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee73b890fca43a3651f22092486e5898862b0b72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="command-line-configuration-wizard-for-the-mqseries-adapter"></a><span data-ttu-id="0e31f-102">Asistente para la configuración de línea de comandos para el adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="0e31f-102">Command-Line Configuration Wizard for the MQSeries Adapter</span></span>
<span data-ttu-id="0e31f-103">El asistente dispone de cuatro opciones para instalar, desinstalar y registrar acciones.</span><span class="sxs-lookup"><span data-stu-id="0e31f-103">The wizard has four options for installing, uninstalling, and logging actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e31f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e31f-104">Syntax</span></span>  
 <span data-ttu-id="0e31f-105">**mqsconfigwiz [/ u] [/i config.xml] [/l logfile] [¿/?]**</span><span class="sxs-lookup"><span data-stu-id="0e31f-105">**mqsconfigwiz [/u] [/i config.xml] [/l logfile] [/?]**</span></span>  
  
|<span data-ttu-id="0e31f-106">Opción</span><span class="sxs-lookup"><span data-stu-id="0e31f-106">Option</span></span>|<span data-ttu-id="0e31f-107">Description</span><span class="sxs-lookup"><span data-stu-id="0e31f-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0e31f-108">**/u**</span><span class="sxs-lookup"><span data-stu-id="0e31f-108">**/u**</span></span>|<span data-ttu-id="0e31f-109">Desinstala MQSAgent.</span><span class="sxs-lookup"><span data-stu-id="0e31f-109">Uninstalls the MQSAgent.</span></span>|  
|<span data-ttu-id="0e31f-110">**/i** *config.xml*</span><span class="sxs-lookup"><span data-stu-id="0e31f-110">**/i** *config.xml*</span></span>|<span data-ttu-id="0e31f-111">Instala MQSAgent utilizando la información en el archivo *config.xml*.</span><span class="sxs-lookup"><span data-stu-id="0e31f-111">Installs the MQSAgent using the information in the file *config.xml*.</span></span>|  
|<span data-ttu-id="0e31f-112">**/l** *archivo de registro*</span><span class="sxs-lookup"><span data-stu-id="0e31f-112">**/l** *logfile*</span></span>|<span data-ttu-id="0e31f-113">Registra acciones en el archivo *archivo de registro*.</span><span class="sxs-lookup"><span data-stu-id="0e31f-113">Logs actions to the file *logfile*.</span></span>|  
|<span data-ttu-id="0e31f-114">**/?**</span><span class="sxs-lookup"><span data-stu-id="0e31f-114">**/?**</span></span>|<span data-ttu-id="0e31f-115">Muestra un cuadro de diálogo que describe las opciones de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0e31f-115">Displays a dialog box describing the command-line options.</span></span>|  
  
 <span data-ttu-id="0e31f-116">El contenido del archivo XML que guarda la información de configuración puede variar en función de la versión de Windows que se esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="0e31f-116">The contents of the XML file that contains the configuration information may vary, depending on the version of Windows you are using.</span></span> <span data-ttu-id="0e31f-117">Para obtener más información acerca del formato de archivo de configuración, consulte [archivo de configuración XML para el adaptador de MQSeries](../core/xml-configuration-file-for-the-mqseries-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="0e31f-117">For more information about the configuration file format, see [XML Configuration File for the MQSeries Adapter](../core/xml-configuration-file-for-the-mqseries-adapter.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e31f-118">El adaptador no funciona mientras se está ejecutando el Asistente para configuración.</span><span class="sxs-lookup"><span data-stu-id="0e31f-118">The adapter does not work while the configuration wizard is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e31f-119">No podrá volver a configurar MQSAgent con el Asistente para configuración de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0e31f-119">You cannot reconfigure MQSAgent with the command-line configuration wizard.</span></span> <span data-ttu-id="0e31f-120">En primer lugar debe ejecutar el Asistente para desinstalar el agente (**/u**), y, a continuación, ejecútelo para configurar (**/i**).</span><span class="sxs-lookup"><span data-stu-id="0e31f-120">You must first run the wizard to uninstall the agent (**/u**), and then run it to configure (**/i**).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e31f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e31f-121">See Also</span></span>  
 [<span data-ttu-id="0e31f-122">Configuración silenciosa del adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="0e31f-122">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)