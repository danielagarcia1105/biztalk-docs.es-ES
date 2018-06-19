---
title: Exportación de certificados | Documentos de Microsoft
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
ms.openlocfilehash: 32dc7b0f73955c080f875eada2705300800df452
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964522"
---
# <a name="exporting-certificates"></a><span data-ttu-id="f1f10-102">Exportación de certificados</span><span class="sxs-lookup"><span data-stu-id="f1f10-102">Exporting Certificates</span></span>
<span data-ttu-id="f1f10-103">En este tema se describe cómo exportar un certificado mediante el Asistente para exportación de certificados.</span><span class="sxs-lookup"><span data-stu-id="f1f10-103">This topic describes how to export a certificate by using the Certificate Export Wizard.</span></span> <span data-ttu-id="f1f10-104">Use este asistente para exportar un certificado público o un certificado privado.</span><span class="sxs-lookup"><span data-stu-id="f1f10-104">Use this wizard to export either a public certificate or a private certificate.</span></span>  
  
### <a name="to-export-a-partner-certificate"></a><span data-ttu-id="f1f10-105">Para exportar un certificado de un socio comercial</span><span class="sxs-lookup"><span data-stu-id="f1f10-105">To export a partner certificate</span></span>  
  
1.  <span data-ttu-id="f1f10-106">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-106">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="f1f10-107">Expanda **Certificados (equipo local)** y **Otras personas**, y haga clic en **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-107">Expand **Certificates (Local Computer)**, expand **Other People**, and then click **Certificates**.</span></span>  
  
3.  <span data-ttu-id="f1f10-108">En el panel derecho, haga clic con el botón secundario en el nombre del certificado, seleccione **Todas las tareas**y, a continuación, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-108">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4.  <span data-ttu-id="f1f10-109">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-109">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="f1f10-110">En la página **Formato de archivo de exportación** , seleccione el formato que desea usar para el archivo.</span><span class="sxs-lookup"><span data-stu-id="f1f10-110">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="f1f10-111">Generalmente, este formato es DER binario codificado x.509 para exportar un archivo codificado en binario o codificado en base 64 x.509 para exportar un archivo codificado en base 64.</span><span class="sxs-lookup"><span data-stu-id="f1f10-111">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f1f10-112">La codificación de un certificado en base 64 le permite usar el certificado en un servidor UNIX.</span><span class="sxs-lookup"><span data-stu-id="f1f10-112">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
6.  <span data-ttu-id="f1f10-113">En la página **Archivo que se va a exportar** , haga clic en **Examinar**, indique la ubicación donde desea almacenar el archivo, escriba el nombre del archivo, haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-113">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-export-the-home-organization-certificate"></a><span data-ttu-id="f1f10-114">Para exportar el certificado de la organización principal</span><span class="sxs-lookup"><span data-stu-id="f1f10-114">To export the home organization certificate</span></span>  
  
1.  <span data-ttu-id="f1f10-115">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **runas/user:\<hospedar servicio\> mmc**, donde \< *hostservice*  \> es el nombre del servicio que asociado al servicio de host cuando instaló [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]y, a continuación, haga clic en **Aceptar** para ejecutar el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] administración Console (MMC) en el contexto del servicio de host.</span><span class="sxs-lookup"><span data-stu-id="f1f10-115">Click **Start**, click **Run**, type **runas /user:\<host service\> mmc**, where \<*hostservice*\> is the name of the service that you associated with the host service when you installed [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], and then click **OK** to run the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC) in the context of the host service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f1f10-116">Ejecute el comando **runas** para asumir la identidad del servicio de host, que se requiere para acceder al certificado de la organización principal.</span><span class="sxs-lookup"><span data-stu-id="f1f10-116">You run the **runas** command to assume the identity of the host service, which is required to access the home-organization certificate.</span></span>  
  
2.  <span data-ttu-id="f1f10-117">Expanda **Certificados: usuario actual**, después **Personal**y, a continuación, haga clic en **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-117">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
3.  <span data-ttu-id="f1f10-118">En el panel derecho, haga clic con el botón secundario en el nombre del certificado, seleccione **Todas las tareas**y, a continuación, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-118">In the right pane, right-click the name of the certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
4.  <span data-ttu-id="f1f10-119">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-119">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="f1f10-120">Para exportar la clave pública asociada con la clave privada de un certificado, deje seleccionado **No, no exportar la clave privada** .</span><span class="sxs-lookup"><span data-stu-id="f1f10-120">To export the public key associated with the private key of a certificate, leave **No, do not export the private key** selected.</span></span> <span data-ttu-id="f1f10-121">Para exportar la clave privada, seleccione **Exportar la clave privada**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-121">To export the private key, select **Yes, export the private key**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f1f10-122">Si selecciona **Exportar la clave privada**, se recomienda encarecidamente no enviar el archivo resultante a ningún socio comercial.</span><span class="sxs-lookup"><span data-stu-id="f1f10-122">If you select **Yes, export the private key**, it is highly recommended that you do not send the resulting file to a partner.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f1f10-123">La opción **Exportar la clave privada** no estará disponible si no hizo que la clave privada fuera exportable cuando la importó por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f1f10-123">The **Yes, export the private key** option will not be available if you did not make the private key exportable when you first imported it.</span></span>  
  
6.  <span data-ttu-id="f1f10-124">En la página **Formato de archivo de exportación** , seleccione el formato que desea usar para el archivo.</span><span class="sxs-lookup"><span data-stu-id="f1f10-124">On the **Export File Format** page, select the format that you want to use for the file.</span></span> <span data-ttu-id="f1f10-125">Generalmente, este formato es DER binario codificado x.509 para exportar un archivo codificado en binario o codificado en base 64 x.509 para exportar un archivo codificado en base 64.</span><span class="sxs-lookup"><span data-stu-id="f1f10-125">This format is generally either DER encoded binary x.509 to export a binary-encoded file, or Base-64 encoded x.509 to export a Base-64 encoded file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f1f10-126">La codificación de un certificado en base 64 le permite usar el certificado en un servidor UNIX.</span><span class="sxs-lookup"><span data-stu-id="f1f10-126">Encoding a certificate in Base-64 lets you use the certificate on a UNIX server.</span></span>  
  
7.  <span data-ttu-id="f1f10-127">En la página **Archivo que se va a exportar** , haga clic en **Examinar**, indique la ubicación donde desea almacenar el archivo, escriba el nombre del archivo, haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f1f10-127">On the **File to Export** page, click **Browse**, locate where you want to store the file, type the name of the file, click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f10-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1f10-128">See Also</span></span>  
 [<span data-ttu-id="f1f10-129">Administración de certificados</span><span class="sxs-lookup"><span data-stu-id="f1f10-129">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)