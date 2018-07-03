---
title: BtarnConfig | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 542ed5729ce4f5ed7ca4a6d453b3169bb1f43d01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991469"
---
# <a name="btarnconfig"></a><span data-ttu-id="8f4a9-102">BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="8f4a9-102">BtarnConfig</span></span>
<span data-ttu-id="8f4a9-103">Use la utilidad BtarnConfig para importar datos de configuración en, o exportar datos de configuración desde un Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] entorno.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-103">You use the BtarnConfig utility to import configuration data into, or export configuration data from, a Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] environment.</span></span> <span data-ttu-id="8f4a9-104">Estos datos de configuración son los datos que se establece mediante la consola de administración de BTARN, incluida la configuración del proceso, organizaciones principales, socios y acuerdos.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-104">This configuration data is the data that you set by using the BTARN Management Console, including process configuration settings, home organizations, partners, and agreements.</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="8f4a9-105">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="8f4a9-105">Location in SDK</span></span>  
 <span data-ttu-id="8f4a9-106">\<*unidad*\>\ archivos de programa (x86)\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK</span><span class="sxs-lookup"><span data-stu-id="8f4a9-106">\<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK</span></span>  

## <a name="running-btarnconfig"></a><span data-ttu-id="8f4a9-107">Ejecutando BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="8f4a9-107">Running BtarnConfig</span></span>  

#### <a name="to-run-btarnconfig"></a><span data-ttu-id="8f4a9-108">Para ejecutar BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="8f4a9-108">To run BtarnConfig</span></span>  

1. <span data-ttu-id="8f4a9-109">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-109">Open a command prompt.</span></span>  

2. <span data-ttu-id="8f4a9-110">Mover a \< *unidad*\>\ archivos de programa (x86)\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-110">Move to \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\\.</span></span>  

3. <span data-ttu-id="8f4a9-111">En el símbolo del sistema, escriba **BtarnConfig**, escriba los modificadores adecuados y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-111">At the command prompt, type **BtarnConfig**, type the appropriate switches, and then press ENTER.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="8f4a9-112">La siguiente sección describe los modificadores.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-112">The following section describes the switches.</span></span>  

## <a name="syntax-for-btarnconfig"></a><span data-ttu-id="8f4a9-113">Sintaxis de BtarnConfig</span><span class="sxs-lookup"><span data-stu-id="8f4a9-113">Syntax for BtarnConfig</span></span>  
 <span data-ttu-id="8f4a9-114">A continuación se muestra la sintaxis que se utiliza para iniciar esta herramienta de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="8f4a9-114">The following shows the syntax that you use to start this command-line tool:</span></span>  

### <a name="syntax-for-importing-configuration-data"></a><span data-ttu-id="8f4a9-115">Sintaxis para importar datos de configuración</span><span class="sxs-lookup"><span data-stu-id="8f4a9-115">Syntax for Importing Configuration Data</span></span>  

```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-for-exporting-configuration-data"></a><span data-ttu-id="8f4a9-116">Sintaxis para exportar datos de configuración</span><span class="sxs-lookup"><span data-stu-id="8f4a9-116">Syntax for Exporting Configuration Data</span></span>  

```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-description"></a><span data-ttu-id="8f4a9-117">Descripción de la sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f4a9-117">Syntax Description</span></span>  
 <span data-ttu-id="8f4a9-118">En la tabla siguiente describe cada parte de la sintaxis que usa la utilidad BtarnConfig.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-118">The following table describes each part of the syntax that the BtarnConfig utility uses.</span></span>  


|       <span data-ttu-id="8f4a9-119">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f4a9-119">Syntax</span></span>       |                                                                                                                          <span data-ttu-id="8f4a9-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f4a9-120">Description</span></span>                                                                                                                          |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8f4a9-121">\<*nombre de archivo*.xml\></span><span class="sxs-lookup"><span data-stu-id="8f4a9-121">\<*filename*.xml\></span></span> | <span data-ttu-id="8f4a9-122">Ruta de acceso completa del archivo para importar o exportar desde.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-122">Full path of the file to import into or export from.</span></span> <span data-ttu-id="8f4a9-123">Si no se proporciona una ruta de acceso, BTARN supone que la ruta de acceso es \< *unidad*\>\ archivos de programa (x86)\\Microsoft BizTalk \<versión\> aceleración de menú SDK DE.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-123">If you do not provide a path, BTARN assumes that the path is \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span> |
|    <span data-ttu-id="8f4a9-124">**E IMPORTACIÓN**</span><span class="sxs-lookup"><span data-stu-id="8f4a9-124">**/IMPORT**</span></span>     |                                                                                          <span data-ttu-id="8f4a9-125">Importa los datos XML de \< *filename*.xml\> en la configuración de BTARN.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-125">Imports the XML data from \<*filename*.xml\> into the BTARN configuration.</span></span>                                                                                           |
|    <span data-ttu-id="8f4a9-126">**/ EXPORT**</span><span class="sxs-lookup"><span data-stu-id="8f4a9-126">**/EXPORT**</span></span>     |                                                                                             <span data-ttu-id="8f4a9-127">Exporta la configuración de BTARN como datos XML a \< *filename*.xml\>.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-127">Exports the BTARN configuration as XML data into \<*filename*.xml\>.</span></span>                                                                                              |
|       <span data-ttu-id="8f4a9-128">**/H**</span><span class="sxs-lookup"><span data-stu-id="8f4a9-128">**/H**</span></span>       |                                                                                                   <span data-ttu-id="8f4a9-129">Importa o exporta datos de configuración de la organización.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-129">Imports or exports home-organization configuration data.</span></span>                                                                                                    |
|       <span data-ttu-id="8f4a9-130">**/P**</span><span class="sxs-lookup"><span data-stu-id="8f4a9-130">**/P**</span></span>       |                                                                                                        <span data-ttu-id="8f4a9-131">Importa o exporta datos de configuración asociado.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-131">Imports or exports partner configuration data.</span></span>                                                                                                         |
|       <span data-ttu-id="8f4a9-132">**/R**</span><span class="sxs-lookup"><span data-stu-id="8f4a9-132">**/R**</span></span>       |                                                                                                        <span data-ttu-id="8f4a9-133">Importa o exporta datos de configuración de proceso.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-133">Imports or exports process configuration data.</span></span>                                                                                                         |
|       <span data-ttu-id="8f4a9-134">**/A**</span><span class="sxs-lookup"><span data-stu-id="8f4a9-134">**/A**</span></span>       |                                                                                                       <span data-ttu-id="8f4a9-135">Importa o exporta datos de configuración del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-135">Imports or exports agreement configuration data.</span></span>                                                                                                        |

## <a name="remarks"></a><span data-ttu-id="8f4a9-136">Notas</span><span class="sxs-lookup"><span data-stu-id="8f4a9-136">Remarks</span></span>  
 <span data-ttu-id="8f4a9-137">Si no se proporciona uno de los **/H**, **/P**, **/R**, o **/A** cambia, el BtarnConfig utilidad importa o exporta todos los datos.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-137">If you do not provide any one of the **/H**, **/P**, **/R**, or **/A** switches, the BtarnConfig utility imports or exports all the data.</span></span> <span data-ttu-id="8f4a9-138">Al exportar todos los datos en una sola operación, BtarnConfig exporta los datos en el archivo XML en el orden siguiente: las organizaciones, la configuración del proceso, socios y acuerdos de inicio.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-138">When you export all the data in one operation, BtarnConfig exports the data into the XML file in the following order: home organizations, partners, process configuration, and agreements.</span></span>  

 <span data-ttu-id="8f4a9-139">Si hay un problema con el archivo que se va a importar desde estructural, BTARN detectará el error durante la fase de validación de esquema y se producirá un error en la operación antes de importaron los datos.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-139">If there is a structural problem with the file that you are importing from, BTARN will detect the error during the schema validation stage, and the operation will fail before any data is imported.</span></span> <span data-ttu-id="8f4a9-140">Si se produce otro error, por ejemplo, está intentando importar un artefacto duplicado o HTTPS es necesario para el acuerdo de PIP, se producirá un error en la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-140">If another error occurs, for example, you are trying to import a duplicate artifact or HTTPS is required for the PIP/agreement, then the import operation will fail.</span></span> <span data-ttu-id="8f4a9-141">Sin embargo, todos los datos se importan hasta que punto permanecerá en la configuración.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-141">However, all the data imported up to that point will remain in the configuration.</span></span>  

 <span data-ttu-id="8f4a9-142">Debe ser un administrador de BizTalk para importar o exportar datos de configuración utilizando BtarnConfig.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-142">You must be a BizTalk administrator to import or export configuration data using BtarnConfig.</span></span> <span data-ttu-id="8f4a9-143">Si no es un administrador de BizTalk, algunas operaciones de importación pueden producir un error debido a problemas de acceso.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-143">If you are not a BizTalk administrator, some import operations may fail because of access issues.</span></span> <span data-ttu-id="8f4a9-144">Sin embargo, otras operaciones de importación en el mismo comando BtarnConfig pueden ser correcta.</span><span class="sxs-lookup"><span data-stu-id="8f4a9-144">However,  other import operations in the same BtarnConfig command may succeed.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8f4a9-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f4a9-145">See Also</span></span>  
 [<span data-ttu-id="8f4a9-146">Utilidades</span><span class="sxs-lookup"><span data-stu-id="8f4a9-146">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
