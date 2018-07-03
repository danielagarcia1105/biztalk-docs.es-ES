---
title: Reemplace la utilidad de Token de clave pública | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Replace Public Key Token Utility
- utilities, Replace Public Key Token Utility
- public key token
ms.assetid: ed8673b9-af06-4bd7-b8b7-7371e4dd0fed
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d546a01d615dbd6dd8146d186e484addcef200b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996285"
---
# <a name="replace-public-key-token-utility"></a><span data-ttu-id="46a72-102">Utilidad para reemplazar el token de clave pública</span><span class="sxs-lookup"><span data-stu-id="46a72-102">Replace Public Key Token Utility</span></span>
<span data-ttu-id="46a72-103">Esta utilidad se puede usar para reemplazar un token de clave pública o una variable de un archivo por un token de clave pública derivado de un archivo de clave de ensamblado de nombre seguro (.snk).</span><span class="sxs-lookup"><span data-stu-id="46a72-103">This utility can be used to replace either a public key token or variable in a file with a public key token derived from a strong name assembly key (.snk) file.</span></span>  
  
 <span data-ttu-id="46a72-104">Esta utilidad puede resultar útil cuando un desarrollador es escribir un script que usa el [referencia de línea de comandos BTSTask](../core/btstask-command-line-reference.md) para implementar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="46a72-104">This utility might be useful when a developer is writing a script that uses the [BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) to deploy an assembly.</span></span> <span data-ttu-id="46a72-105">Para que la implementación se realice correctamente, se debe proporcionar el nombre completo del ensamblado, que incluye el token de clave pública correspondiente.</span><span class="sxs-lookup"><span data-stu-id="46a72-105">For the deployment to succeed, the fully qualified name of the assembly must be provided, which includes its public key token.</span></span> <span data-ttu-id="46a72-106">El token de clave pública de un ensamblado se extrae de un archivo .snk y se asigna al ensamblado cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="46a72-106">The public key token for an assembly is extracted from an .snk file and assigned to the assembly when it is built.</span></span> <span data-ttu-id="46a72-107">Sin embargo, antes de que el ensamblado se implemente en un nuevo entorno, a menudo se vuelve a generar (compilar) con un token de clave pública diferente.</span><span class="sxs-lookup"><span data-stu-id="46a72-107">Before the assembly is deployed into a new environment, however, it is often rebuilt using a different public key token.</span></span> <span data-ttu-id="46a72-108">Como resultado, es posible que el programador desconozca el token de clave pública que se usará para el ensamblado cuando se ejecute la secuencia de comandos de implementación.</span><span class="sxs-lookup"><span data-stu-id="46a72-108">As a result, the developer may not know what public key token will be used for the assembly when the deployment script is run.</span></span>  
  
 <span data-ttu-id="46a72-109">La utilidad para reemplazar el token de clave pública se puede usar de dos formas en esta situación:</span><span class="sxs-lookup"><span data-stu-id="46a72-109">There are two ways that you can use the Replace Public Key Token utility to address this situation:</span></span>  
  
-   <span data-ttu-id="46a72-110">**Escenario 1.**</span><span class="sxs-lookup"><span data-stu-id="46a72-110">**Scenario 1.**</span></span> <span data-ttu-id="46a72-111">En la secuencia de comandos de implementación, el programador puede usar un token de clave pública o un marcador de posición que represente al token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="46a72-111">In the deployment script, the developer can use either a public key token or a placeholder representing the public key token.</span></span> <span data-ttu-id="46a72-112">Antes de ejecutar la secuencia de comandos, un usuario puede ejecutar la utilidad para reemplazar el token de clave pública para sustituir el token de clave pública o el marcador de posición del archivo de secuencia de comandos por el token de clave pública extraído del archivo .snk que se usó para crear el ensamblado para el entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="46a72-112">Before running the script, a user can run the Replace Public Key Token utility to substitute the public key token or placeholder in the script file with the public key token extracted from the .snk file that was used to build the assembly for the destination environment.</span></span>  
  
-   <span data-ttu-id="46a72-113">**Escenario 2.**</span><span class="sxs-lookup"><span data-stu-id="46a72-113">**Scenario 2.**</span></span> <span data-ttu-id="46a72-114">El programador puede configurar la secuencia de comandos para sustituir automáticamente el nuevo token de clave pública, como sigue: al principio de la secuencia de comandos, invoque la utilidad de Token de clave pública y hacer que apunte a un archivo .snk que contiene el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="46a72-114">The developer can configure the script to automatically substitute the new public key token, as follows: At the start of the script, invoke the Replace Public Key Token utility and point it to a .snk file that contains the public key token.</span></span> <span data-ttu-id="46a72-115">Dentro de la secuencia de comandos, use la variable de entorno %NEWTOKEN% para representar el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="46a72-115">Within the script, use the environment variable %NEWTOKEN% to represent the public key token.</span></span> <span data-ttu-id="46a72-116">Cuando se ejecute la secuencia de comandos, la utilidad extraerá el valor del token de clave pública del archivo .snk y lo establecerá en una variable de entorno %NEWTOKEN%.</span><span class="sxs-lookup"><span data-stu-id="46a72-116">When the script runs, the utility extracts the value of the public key token from the .snk file and sets it into an environment variable %NEWTOKEN%.</span></span> <span data-ttu-id="46a72-117">Al ejecutar la secuencia de comandos, cada instancia de %NEWTOKEN% se sustituirá con el token de clave pública del archivo .snk especificado.</span><span class="sxs-lookup"><span data-stu-id="46a72-117">When the script runs, each instance of %NEWTOKEN% will be with substituted with the public key token from the specified .snk file.</span></span> <span data-ttu-id="46a72-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46a72-118">For example:</span></span>  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a><span data-ttu-id="46a72-119">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="46a72-119">Location in SDK</span></span>  
 <span data-ttu-id="46a72-120">La utilidad para reemplazar el token de clave pública se encuentra en:</span><span class="sxs-lookup"><span data-stu-id="46a72-120">The Replace Public Key Token utility is located in:</span></span>  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="46a72-121">SDK\Utilities\ReplacePublicKeyToken\\.</span><span class="sxs-lookup"><span data-stu-id="46a72-121">SDK\Utilities\ReplacePublicKeyToken\\.</span></span>  
  
 <span data-ttu-id="46a72-122">La utilidad para reemplazar el token de clave pública consta de tres archivos:</span><span class="sxs-lookup"><span data-stu-id="46a72-122">The Replace Public Key Token utility comprises three files:</span></span>  
  
-   <span data-ttu-id="46a72-123">ReplacePKT.bat</span><span class="sxs-lookup"><span data-stu-id="46a72-123">ReplacePKT.bat</span></span>  
  
-   <span data-ttu-id="46a72-124">ReplacePKT.vbs</span><span class="sxs-lookup"><span data-stu-id="46a72-124">ReplacePKT.vbs</span></span>  
  
-   <span data-ttu-id="46a72-125">ReplacePKT.wsf</span><span class="sxs-lookup"><span data-stu-id="46a72-125">ReplacePKT.wsf</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="46a72-126">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="46a72-126">Procedures</span></span>  
 <span data-ttu-id="46a72-127">Siga el procedimiento siguiente para reemplazar todas las instancias de un token de clave pública o un marcador de posición de un archivo con el token de clave pública extraído de un archivo .snk, tal como se describe en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="46a72-127">Use the following procedure to replace all instances of a public key token or a placeholder in a file with a public key token extracted from an .snk file, as described in Scenario 1.</span></span>  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a><span data-ttu-id="46a72-128">Para reemplazar instancias de un token de clave pública o un marcador de posición de un archivo</span><span class="sxs-lookup"><span data-stu-id="46a72-128">To replace instances of a public key token or a placeholder in a file</span></span>  
  
1. <span data-ttu-id="46a72-129">Asegúrese de que los tres archivos de la utilidad para reemplazar el token de clave pública (ReplacePKT.bat, ReplacePKT.vbs y ReplacePKT.wsf), el archivo de secuencia de comandos y el archivo .snk están disponibles en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="46a72-129">Make sure that the three Replace Public Key Token utility files (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf), the script file, and the .snk file are all available from the local computer.</span></span>  
  
2. <span data-ttu-id="46a72-130">En una ventana de comandos, cambie el directorio a la carpeta que contiene los archivos de la utilidad para reemplazar el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="46a72-130">In a command window, change the directory to the folder containing the Replace Public Key utility files.</span></span>  
  
3. <span data-ttu-id="46a72-131">Desde el símbolo del sistema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="46a72-131">From a command prompt, run the following command:</span></span>  
  
4. <span data-ttu-id="46a72-132">**ReplacePKT \<**  *archivo .snk* **\> \<** *token de clave pública antiguo* **\> \<** *archivo para reemplazar* **\>**</span><span class="sxs-lookup"><span data-stu-id="46a72-132">**ReplacePKT \<** *.snk file* **\> \<** *old public key token* **\> \<** *file to replace* **\>**</span></span>  
  
   |<span data-ttu-id="46a72-133">Opción</span><span class="sxs-lookup"><span data-stu-id="46a72-133">Option</span></span>|<span data-ttu-id="46a72-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="46a72-134">Description</span></span>|  
   |------------|-----------------|  
   |<span data-ttu-id="46a72-135">**\<** *archivo .snk* **\>**</span><span class="sxs-lookup"><span data-stu-id="46a72-135">**\<** *.snk file* **\>**</span></span>|<span data-ttu-id="46a72-136">Ruta de acceso completa del archivo .snk que contiene el token de clave pública que desea sustituir por el token de clave pública o marcador de posición existente.</span><span class="sxs-lookup"><span data-stu-id="46a72-136">Full path of the .snk file containing the public key token that you want substitute for the existing public key token or placeholder.</span></span>|  
   |<span data-ttu-id="46a72-137">**\<** *token de clave pública antiguo* **\>**</span><span class="sxs-lookup"><span data-stu-id="46a72-137">**\<** *old public key token* **\>**</span></span>|<span data-ttu-id="46a72-138">Token de clave pública o marcador de posición que desea reemplazar.</span><span class="sxs-lookup"><span data-stu-id="46a72-138">Public key token or placeholder that you want to replace.</span></span>|  
   |<span data-ttu-id="46a72-139">**\<** *archivo para reemplazar* **\>**</span><span class="sxs-lookup"><span data-stu-id="46a72-139">**\<** *file to replace* **\>**</span></span>|<span data-ttu-id="46a72-140">Ruta de acceso completa del archivo en el que desea reemplazar el token de clave pública o marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="46a72-140">Full path of the file in which you want to replace the public key token or placeholder.</span></span>|  
  
    <span data-ttu-id="46a72-141">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46a72-141">Example:</span></span>  
  
    <span data-ttu-id="46a72-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span><span class="sxs-lookup"><span data-stu-id="46a72-142">**ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**</span></span>  
  
   <span data-ttu-id="46a72-143">Siga el procedimiento siguiente para establecer automáticamente una variable de entorno en una secuencia de comandos que use un token de clave pública derivado de un archivo .snk, tal como se describe en el escenario 2.</span><span class="sxs-lookup"><span data-stu-id="46a72-143">Use the following procedure to automatically set an environment variable in a script that uses a public key token derived from an .snk file, as described in Scenario 2.</span></span>  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a><span data-ttu-id="46a72-144">Para establecer una variable de entorno que use un token de clave pública</span><span class="sxs-lookup"><span data-stu-id="46a72-144">To set an environment variable that uses a public key token</span></span>  
  
1.  <span data-ttu-id="46a72-145">Agregue la siguiente línea de código al principio del archivo de comandos:</span><span class="sxs-lookup"><span data-stu-id="46a72-145">At the beginning of your script file, add the following line of code:</span></span>  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     <span data-ttu-id="46a72-146">Donde \< *filename* \> es el nombre del archivo .snk del que se deriva el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="46a72-146">Where \<*filename*\> is the name of the .snk file from which to derive the public key token.</span></span>  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  <span data-ttu-id="46a72-147">En el archivo de script, utilice `%NEWTOKEN%` para representar el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="46a72-147">In your script file, use `%NEWTOKEN%` to represent the public key token.</span></span>  
  
     <span data-ttu-id="46a72-148">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="46a72-148">Example:</span></span>  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  <span data-ttu-id="46a72-149">Cuando entregue el archivo de secuencia de comandos a los usuarios, incluya los tres archivos de la utilidad para reemplazar el token de clave pública (ReplacePKT.bat, ReplacePKT.vbs y ReplacePKT.wsf).</span><span class="sxs-lookup"><span data-stu-id="46a72-149">When you deliver your script file to your users, include the three files that comprise the Replace Public Key Token utility (ReplacePKT.bat, ReplacePKT.vbs, ReplacePKT.wsf).</span></span> <span data-ttu-id="46a72-150">Asegúrese de que los usuarios de la secuencia de comandos, copian todos los archivos en la misma carpeta del sistema de archivos antes de ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="46a72-150">Make sure that users of your script copy all of the files to the same folder on the file system before running your script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a72-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="46a72-151">See Also</span></span>  
 [<span data-ttu-id="46a72-152">Utilidades del SDK</span><span class="sxs-lookup"><span data-stu-id="46a72-152">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)