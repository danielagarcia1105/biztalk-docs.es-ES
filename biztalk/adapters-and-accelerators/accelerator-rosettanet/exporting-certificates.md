---
title: Exportación de certificados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f5a4390cc62fdb46cbad9993a106d98163c0838
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975869"
---
# <a name="exporting-certificates"></a><span data-ttu-id="40c7d-102">Exportación de certificados</span><span class="sxs-lookup"><span data-stu-id="40c7d-102">Exporting Certificates</span></span>
<span data-ttu-id="40c7d-103">En este tema se describe cómo exportar un certificado mediante el Asistente para exportación de certificados.</span><span class="sxs-lookup"><span data-stu-id="40c7d-103">This topic describes how to export a certificate by using the Certificate Export Wizard.</span></span> <span data-ttu-id="40c7d-104">Use este asistente para exportar un certificado público o un certificado privado.</span><span class="sxs-lookup"><span data-stu-id="40c7d-104">Use this wizard to export either a public certificate or a private certificate.</span></span>  
  
### <a name="to-export-a-partner-certificate"></a><span data-ttu-id="40c7d-105">Para exportar un certificado de un socio comercial</span><span class="sxs-lookup"><span data-stu-id="40c7d-105">To export a partner certificate</span></span>  
  
1. <span data-ttu-id="40c7d-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-106">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="40c7d-107">Expanda **Certificados (equipo local)** y **Otras personas**, y haga clic en **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-107">Expand **Certificates (Local Computer)**, expand **Other People**, and then click **Certificates**.</span></span>  
  
3. <span data-ttu-id="40c7d-108">En el panel derecho, haga clic con el botón secundario en el nombre del certificado, seleccione **Todas las tareas**y, a continuación, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-108">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="40c7d-109">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-109">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="40c7d-110">En la página **Formato de archivo de exportación** , seleccione el formato que desea usar para el archivo.</span><span class="sxs-lookup"><span data-stu-id="40c7d-110">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="40c7d-111">Generalmente, este formato es DER binario codificado x.509 para exportar un archivo codificado en binario o codificado en base 64 x.509 para exportar un archivo codificado en base 64.</span><span class="sxs-lookup"><span data-stu-id="40c7d-111">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="40c7d-112">La codificación de un certificado en base 64 le permite usar el certificado en un servidor UNIX.</span><span class="sxs-lookup"><span data-stu-id="40c7d-112">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
6. <span data-ttu-id="40c7d-113">En la página **Archivo que se va a exportar** , haga clic en **Examinar**, indique la ubicación donde desea almacenar el archivo, escriba el nombre del archivo, haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-113">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-export-the-home-organization-certificate"></a><span data-ttu-id="40c7d-114">Para exportar el certificado de la organización principal</span><span class="sxs-lookup"><span data-stu-id="40c7d-114">To export the home organization certificate</span></span>  
  
1. <span data-ttu-id="40c7d-115">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **runas/user:\<hospedar servicio\> mmc**, donde \< *hostservice*  \> es el nombre del servicio que ha asociado con el servicio de host cuando instaló Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]y, a continuación, haga clic en **Aceptar** para ejecutar Microsoft Management Console (MMC) en el contexto del servicio de host.</span><span class="sxs-lookup"><span data-stu-id="40c7d-115">Click **Start**, click **Run**, type **runas /user:\<host service\> mmc**, where \<*hostservice*\> is the name of the service that you associated with the host service when you installed Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], and then click **OK** to run the Microsoft Management Console (MMC) in the context of the host service.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="40c7d-116">Ejecute el comando **runas** para asumir la identidad del servicio de host, que se requiere para acceder al certificado de la organización principal.</span><span class="sxs-lookup"><span data-stu-id="40c7d-116">You run the **runas** command to assume the identity of the host service, which is required to access the home-organization certificate.</span></span>  
  
2. <span data-ttu-id="40c7d-117">Expanda **Certificados: usuario actual**, después **Personal**y, a continuación, haga clic en **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-117">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
3. <span data-ttu-id="40c7d-118">En el panel derecho, haga clic con el botón secundario en el nombre del certificado, seleccione **Todas las tareas**y, a continuación, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-118">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4. <span data-ttu-id="40c7d-119">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-119">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5. <span data-ttu-id="40c7d-120">Para exportar la clave pública asociada con la clave privada de un certificado, deje seleccionado **No, no exportar la clave privada** .</span><span class="sxs-lookup"><span data-stu-id="40c7d-120">To export the public key associated with the private key of a certificate, leave **No, do not export the private key** selected.</span></span> <span data-ttu-id="40c7d-121">Para exportar la clave privada, seleccione **Exportar la clave privada**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-121">To export the private key, select **Yes, export the private key**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="40c7d-122">Si selecciona **Exportar la clave privada**, se recomienda encarecidamente no enviar el archivo resultante a ningún socio comercial.</span><span class="sxs-lookup"><span data-stu-id="40c7d-122">If you select **Yes, export the private key**, it is highly recommended that you do not send the resulting file to a partner.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="40c7d-123">La opción **Exportar la clave privada** no estará disponible si no hizo que la clave privada fuera exportable cuando la importó por primera vez.</span><span class="sxs-lookup"><span data-stu-id="40c7d-123">The **Yes, export the private key** option will not be available if you did not make the private key exportable when you first imported it.</span></span>  
  
6. <span data-ttu-id="40c7d-124">En la página **Formato de archivo de exportación** , seleccione el formato que desea usar para el archivo.</span><span class="sxs-lookup"><span data-stu-id="40c7d-124">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="40c7d-125">Generalmente, este formato es DER binario codificado x.509 para exportar un archivo codificado en binario o codificado en base 64 x.509 para exportar un archivo codificado en base 64.</span><span class="sxs-lookup"><span data-stu-id="40c7d-125">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="40c7d-126">La codificación de un certificado en base 64 le permite usar el certificado en un servidor UNIX.</span><span class="sxs-lookup"><span data-stu-id="40c7d-126">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
7. <span data-ttu-id="40c7d-127">En la página **Archivo que se va a exportar** , haga clic en **Examinar**, indique la ubicación donde desea almacenar el archivo, escriba el nombre del archivo, haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="40c7d-127">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c7d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c7d-128">See Also</span></span>  
 [<span data-ttu-id="40c7d-129">Administración de certificados</span><span class="sxs-lookup"><span data-stu-id="40c7d-129">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)