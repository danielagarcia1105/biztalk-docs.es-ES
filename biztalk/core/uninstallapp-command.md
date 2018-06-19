---
title: Comando UninstallApp | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f45c9530-8138-40f1-b279-1428c5a7fbbc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea94335882ffbcf01b69c450ef4a5eb80ef4fa3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286788"
---
# <a name="uninstallapp-command"></a><span data-ttu-id="f3ece-102">UninstallApp (comando)</span><span class="sxs-lookup"><span data-stu-id="f3ece-102">UninstallApp Command</span></span>
<span data-ttu-id="f3ece-103">Desinstala una aplicación de BizTalk desde el equipo local y también quita la aplicación de la lista de programas en Agregar o quitar programas del Panel de control.</span><span class="sxs-lookup"><span data-stu-id="f3ece-103">Uninstalls a BizTalk application from the local computer and also removes the application from the list of programs in Add or Remove Programs in Control Panel.</span></span> <span data-ttu-id="f3ece-104">Este comando tiene el mismo efecto que si se quita una aplicación mediante Agregar o quitar programas.</span><span class="sxs-lookup"><span data-stu-id="f3ece-104">This command has the same effect as removing an application by using Add or Remove Programs.</span></span> <span data-ttu-id="f3ece-105">Si se han instalado varios archivos .msi para esta aplicación, se desinstalan todos los elementos instalados por todos los archivos .msi.</span><span class="sxs-lookup"><span data-stu-id="f3ece-105">If multiple .msi files have been installed for this application, all of the items installed by all of the .msi files are uninstalled.</span></span>  
  
 <span data-ttu-id="f3ece-106">El nombre de aplicación que especifica para este comando debe coincidir con el nombre de aplicación tal y como se muestra en Agregar o quitar programas.</span><span class="sxs-lookup"><span data-stu-id="f3ece-106">The application name that you specify for this command must match the name of the application as displayed in Add or Remove Programs.</span></span> <span data-ttu-id="f3ece-107">Si no está seguro de que el nombre de la aplicación, puede usar el **ListPackage** comando para obtenerlo, tal y como se describe en [comando ListPackage](../core/listpackage-command.md).</span><span class="sxs-lookup"><span data-stu-id="f3ece-107">If you are unsure of the application name, you can use the **ListPackage** command to obtain it, as described in [ListPackage Command](../core/listpackage-command.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f3ece-108">Aunque es posible desinstalar una aplicación haciendo doble clic en el archivo .msi, no es compatible realizar esto.</span><span class="sxs-lookup"><span data-stu-id="f3ece-108">Although it is possible to uninstall an application by double-clicking the .msi file, doing this is not supported.</span></span> <span data-ttu-id="f3ece-109">Se debe a que varios archivos .msi se pueden instalar para la misma aplicación y utilizar este método no desinstalará todos los elementos asociados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3ece-109">This is because multiple .msi files can be installed for the same application, and using this method will not uninstall all of the items associated with the application.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f3ece-110">Uso</span><span class="sxs-lookup"><span data-stu-id="f3ece-110">Usage</span></span>  
 <span data-ttu-id="f3ece-111">**/ ApplicationName BTSTask UninstallApp:** *valor*</span><span class="sxs-lookup"><span data-stu-id="f3ece-111">**BTSTask UninstallApp /ApplicationName:** *value*</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="f3ece-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3ece-112">Parameters</span></span>  
  
|<span data-ttu-id="f3ece-113">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f3ece-113">Parameter</span></span>|<span data-ttu-id="f3ece-114">Necesario</span><span class="sxs-lookup"><span data-stu-id="f3ece-114">Required</span></span>|<span data-ttu-id="f3ece-115">Description</span><span class="sxs-lookup"><span data-stu-id="f3ece-115">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="f3ece-116">**/ ApplicationName** (o **/A**, vea la sección Comentarios)</span><span class="sxs-lookup"><span data-stu-id="f3ece-116">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="f3ece-117">Sí</span><span class="sxs-lookup"><span data-stu-id="f3ece-117">Yes</span></span>|<span data-ttu-id="f3ece-118">Nombre de la aplicación de BizTalk que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="f3ece-118">Name of the BizTalk application to uninstall.</span></span> <span data-ttu-id="f3ece-119">Si el nombre incluye espacios, debe encerrarlo entre comillas dobles (").</span><span class="sxs-lookup"><span data-stu-id="f3ece-119">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="f3ece-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3ece-120">Sample</span></span>  
 <span data-ttu-id="f3ece-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span><span class="sxs-lookup"><span data-stu-id="f3ece-121">**BTSTask UninstallApp /ApplicationName:MyApplication**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3ece-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3ece-122">Remarks</span></span>  
 <span data-ttu-id="f3ece-123">Los parámetros no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f3ece-123">Parameters are not case-sensitive.</span></span> <span data-ttu-id="f3ece-124">No es necesario escribir el nombre de todo el parámetro para especificarlo; puede escribir las primeras letras del nombre de parámetro que lo identifican sin ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="f3ece-124">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ece-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3ece-125">See Also</span></span>  
 <span data-ttu-id="f3ece-126">[Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f3ece-126">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="f3ece-127">Cómo desinstalar una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="f3ece-127">How to Uninstall a BizTalk Application</span></span>](../core/how-to-uninstall-a-biztalk-application.md)