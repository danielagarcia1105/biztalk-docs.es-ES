---
title: 'Paso 2: Crear Public y Private certificados | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating certificates
- public certificates
- certificates, public certificates
- creating, certificates
- private certificates
ms.assetid: 0a925d89-03d9-41fe-907b-85a6ae42362a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d9653f1ec72e56b225142d2d6c9fdff24198e7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-public-and-private-certificates"></a><span data-ttu-id="9c9d1-102">Paso 2: Crear Public y Private certificados</span><span class="sxs-lookup"><span data-stu-id="9c9d1-102">Step 2: Creating Public and Private Certificates</span></span>
<span data-ttu-id="9c9d1-103">En este paso, utilice la entidad de certificación que se creó en [paso 1: crear una entidad de certificación &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) para generar los certificados públicos y privados que utilizan las organizaciones de Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-103">In this step, you use the Certification Authority created in [Step 1: Creating a Certification Authority &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) to generate the public and private certificates that the Contoso and Fabrikam organizations use.</span></span>  
  
### <a name="to-generate-the-contoso-and-fabrikam-encryption-certificates"></a><span data-ttu-id="9c9d1-104">Para generar los certificados de cifrado de Contoso y Fabrikam</span><span class="sxs-lookup"><span data-stu-id="9c9d1-104">To generate the Contoso and Fabrikam encryption certificates</span></span>  
  
1.  <span data-ttu-id="9c9d1-105">En el equipo que utiliza como la entidad de certificación, en Internet Explorer, busque y abra http://<contoso_computername>/certsrv.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-105">On the computer you used as the Certification Authority, in Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  
  
2.  <span data-ttu-id="9c9d1-106">En el **bienvenida** página, haga clic en **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-106">On the **Welcome** page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="9c9d1-107">En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-107">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="9c9d1-108">En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-108">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  
  
5.  <span data-ttu-id="9c9d1-109">En el **solicitud de certificado avanzada** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c9d1-109">On the **Advanced Certificate Request** page, do the following:</span></span>  
  
    |<span data-ttu-id="9c9d1-110">Use</span><span class="sxs-lookup"><span data-stu-id="9c9d1-110">Use this</span></span>|<span data-ttu-id="9c9d1-111">Para</span><span class="sxs-lookup"><span data-stu-id="9c9d1-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9c9d1-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-112">**Name**</span></span>|<span data-ttu-id="9c9d1-113">Tipo de **Fabrikam cifrado**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-113">Type **Fabrikam Encryption**.</span></span>|  
    |<span data-ttu-id="9c9d1-114">**Correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-114">**E-Mail**</span></span>|<span data-ttu-id="9c9d1-115">Tipo de  **jdoe@fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="9c9d1-115">Type **jdoe@fabrikam.com**.</span></span>|  
    |<span data-ttu-id="9c9d1-116">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-116">**Company**</span></span>|<span data-ttu-id="9c9d1-117">Tipo de **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-117">Type **Fabrikam**.</span></span>|  
    |<span data-ttu-id="9c9d1-118">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-118">**Department**</span></span>|<span data-ttu-id="9c9d1-119">Tipo de **prueba**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-119">Type **Test**.</span></span>|  
    |<span data-ttu-id="9c9d1-120">**City**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-120">**City**</span></span>|<span data-ttu-id="9c9d1-121">Tipo de **prueba**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-121">Type **Test**.</span></span>|  
    |<span data-ttu-id="9c9d1-122">**State**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-122">**State**</span></span>|<span data-ttu-id="9c9d1-123">Tipo de **prueba**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-123">Type **Test**.</span></span>|  
    |<span data-ttu-id="9c9d1-124">**País o región**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-124">**Country/Region**</span></span>|<span data-ttu-id="9c9d1-125">Tipo de **US**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-125">Type **US**.</span></span>|  
    |<span data-ttu-id="9c9d1-126">**Tipo de certificado necesario**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-126">**Type of Certificate Needed**</span></span>|<span data-ttu-id="9c9d1-127">Seleccione **certificado de protección de correo electrónico** desde la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-127">Select **E-Mail Protection Certificate** from the drop down list.</span></span>|  
    |<span data-ttu-id="9c9d1-128">**Uso de claves**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-128">**Key Usage**</span></span>|<span data-ttu-id="9c9d1-129">Seleccione el **Exchange** opción.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-129">Select the **Exchange** option.</span></span>|  
    |<span data-ttu-id="9c9d1-130">**Opciones de clave adicionales**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-130">**Additional Key Options**</span></span>|<span data-ttu-id="9c9d1-131">Marque las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9c9d1-131">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="9c9d1-132">-   **Marcar esta clave como exportable**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-132">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="9c9d1-133">-   **Almacenar el certificado en el almacén de certificados del equipo local**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-133">-   **Store certificate in the local computer certificate store**</span></span>|  
    |<span data-ttu-id="9c9d1-134">**Nombre descriptivo**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-134">**Friendly Name**</span></span>|<span data-ttu-id="9c9d1-135">Tipo de **Fabrikam cifrado**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-135">Type **Fabrikam Encryption**.</span></span>|  
  
6.  <span data-ttu-id="9c9d1-136">Haga clic en **enviar**y, a continuación, haga clic en **Sí** en **confirmación de acceso Web** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-136">Click **Submit**, and then click **Yes** in **Web Access Confirmation** dialog box.</span></span>  
  
7.  <span data-ttu-id="9c9d1-137">En el **certificado emitido** página, haga clic en **instalar este certificado**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-137">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  
  
8.  <span data-ttu-id="9c9d1-138">Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación de** sección y la **Nombre_descriptivo** cuadro a **Contoso Cifrado**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-138">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Encryption**.</span></span>  
  
### <a name="to-generate-the-contoso-and-fabrikam-signing-certificates"></a><span data-ttu-id="9c9d1-139">Para generar los Contoso y Fabrikam certificados de firma</span><span class="sxs-lookup"><span data-stu-id="9c9d1-139">To generate the Contoso and Fabrikam Signing Certificates</span></span>  
  
1.  <span data-ttu-id="9c9d1-140">En Internet Explorer, busque y abra http://<contoso_computername>/certsrv.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-140">In Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  
  
2.  <span data-ttu-id="9c9d1-141">En el **bienvenida** página, haga clic en **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-141">On the **Welcome** page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="9c9d1-142">En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-142">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="9c9d1-143">En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-143">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  
  
5.  <span data-ttu-id="9c9d1-144">En el **solicitud de certificado avanzada** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c9d1-144">On the **Advanced Certificate Request** page, do the following:</span></span>  
  
    |<span data-ttu-id="9c9d1-145">Use</span><span class="sxs-lookup"><span data-stu-id="9c9d1-145">Use this</span></span>|<span data-ttu-id="9c9d1-146">Para</span><span class="sxs-lookup"><span data-stu-id="9c9d1-146">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9c9d1-147">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-147">**Name**</span></span>|<span data-ttu-id="9c9d1-148">Tipo de **Fabrikam firma**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-148">Type **Fabrikam Signature**.</span></span>|  
    |<span data-ttu-id="9c9d1-149">**Correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-149">**E-Mail**</span></span>|<span data-ttu-id="9c9d1-150">Tipo de  **jdoe@fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="9c9d1-150">Type **jdoe@fabrikam.com**.</span></span>|  
    |<span data-ttu-id="9c9d1-151">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-151">**Company**</span></span>|<span data-ttu-id="9c9d1-152">Tipo de **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-152">Type **Fabrikam**.</span></span>|  
    |<span data-ttu-id="9c9d1-153">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-153">**Department**</span></span>|<span data-ttu-id="9c9d1-154">Tipo de **prueba**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-154">Type **Test**.</span></span>|  
    |<span data-ttu-id="9c9d1-155">**City**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-155">**City**</span></span>|<span data-ttu-id="9c9d1-156">Tipo de **prueba**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-156">Type **Test**.</span></span>|  
    |<span data-ttu-id="9c9d1-157">**State**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-157">**State**</span></span>|<span data-ttu-id="9c9d1-158">Tipo de **prueba**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-158">Type **Test**.</span></span>|  
    |<span data-ttu-id="9c9d1-159">**País o región**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-159">**Country/Region**</span></span>|<span data-ttu-id="9c9d1-160">Tipo de **US**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-160">Type **US**.</span></span>|  
    |<span data-ttu-id="9c9d1-161">**Tipo de certificado necesario**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-161">**Type of Certificate Needed**</span></span>|<span data-ttu-id="9c9d1-162">Seleccione **certificado de protección de correo electrónico**.de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-162">Select **E-Mail Protection Certificate**.from the drop down list.</span></span>|  
    |<span data-ttu-id="9c9d1-163">**Uso de claves**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-163">**Key Usage**</span></span>|<span data-ttu-id="9c9d1-164">Seleccione el **firma** opción.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-164">Select the **Signature** option.</span></span>|  
    |<span data-ttu-id="9c9d1-165">**Opciones de clave adicionales**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-165">**Additional Key Options**</span></span>|<span data-ttu-id="9c9d1-166">Marque las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9c9d1-166">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="9c9d1-167">-   **Marcar esta clave como exportable**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-167">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="9c9d1-168">-   **Almacenar el certificado en el almacén de certificados del equipo local**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-168">-   **Store certificate in the local computer certificate store**</span></span>|  
    |<span data-ttu-id="9c9d1-169">**Nombre descriptivo**</span><span class="sxs-lookup"><span data-stu-id="9c9d1-169">**Friendly Name**</span></span>|<span data-ttu-id="9c9d1-170">Tipo de **Fabrikam firma**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-170">Type **Fabrikam Signature**.</span></span>|  
  
6.  <span data-ttu-id="9c9d1-171">Haga clic en **enviar**y, a continuación, haga clic en **Sí** cuando se le pregunte para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-171">Click **Submit**, and then click **Yes** when asked to request the certificate.</span></span>  
  
7.  <span data-ttu-id="9c9d1-172">En el **certificado emitido** página, haga clic en **instalar este certificado**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-172">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  
  
8.  <span data-ttu-id="9c9d1-173">Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación de** sección y la **Nombre_descriptivo** cuadro a **Contoso Firma**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-173">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Signature**.</span></span>  
  
### <a name="to-generate-private-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="9c9d1-174">Para generar certificados privados para los certificados de firma y cifrado</span><span class="sxs-lookup"><span data-stu-id="9c9d1-174">To generate private certificates for the Encryption and Signature certificates</span></span>  
  
1.  <span data-ttu-id="9c9d1-175">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **MMC**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-175">Click **Start**, click **Run**, type **MMC**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9c9d1-176">En la ventana Consola1, en el **archivo** menú, haga clic en **agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-176">In the Console1 window, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="9c9d1-177">En el cuadro de diálogo Agregar o quitar complemento, en el **independiente** , haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-177">In the Add/Remove Snap-in dialog box, on the **Standalone** tab, click **Add**.</span></span>  
  
4.  <span data-ttu-id="9c9d1-178">En el cuadro de diálogo Add Standalone Snap-in, seleccione la **certificados** complemento desde la **complementos Standalone disponibles** lista y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-178">In the Add Standalone Snap-in dialog box, select the **Certificates** snap-in from the **Available Standalone Snap-ins** list, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="9c9d1-179">En el cuadro de diálogo del complemento de certificados, seleccione **mi cuenta de usuario**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-179">In the Certificates snap-in dialog box, select **My user account**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="9c9d1-180">En el cuadro de diálogo Seleccionar equipo, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-180">In the Select Computer dialog box, click **Finish**.</span></span>  
  
7.  <span data-ttu-id="9c9d1-181">En el cuadro de diálogo Add Standalone Snap-in, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-181">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  
  
8.  <span data-ttu-id="9c9d1-182">En el cuadro de diálogo Agregar o quitar complemento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-182">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="9c9d1-183">En la ventana Consola1, expanda **certificados (equipo Local)**, expanda **Personal**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-183">In the Console1 window, expand **Certificates (Local Computer)**, expand **Personal**, and then click **Certificates**.</span></span>  
  
10. <span data-ttu-id="9c9d1-184">En el panel derecho, haga clic en el **Fabrikam cifrado** de certificados, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-184">In the right pane, right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
11. <span data-ttu-id="9c9d1-185">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-185">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
12. <span data-ttu-id="9c9d1-186">En el **exportar la clave privada** página, seleccione **Sí, exportar la clave privada**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-186">On the **Export Private Key** page, select **Yes, export the private key**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="9c9d1-187">En el **Exportar formato de archivo** página, asegúrese de que **Personal Information Exchange** es la única opción seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-187">On the **Export File Format** page, make sure that **Personal Information Exchange** is the only option selected, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="9c9d1-188">En el **contraseña** página, en la **contraseña** y **Confirmar contraseña** cuadros, escriba **MiSecreto**y, a continuación, haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="9c9d1-188">On the **Password** page, in the **Password** and **Confirm Password** boxes, type **mysecret**, and then click **Next**.</span></span>  
  
15. <span data-ttu-id="9c9d1-189">En el **archivo de exportación** página, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-189">On the **File To Export** page, click **Browse**.</span></span>  
  
16. <span data-ttu-id="9c9d1-190">En el **Guardar como** cuadro de diálogo, guarde el certificado con la ruta de acceso de archivo  *\<unidad >*: \Certs\Fabrikam Encryption.pfx privada.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-190">In the **Save As** dialog box, save the certificate using the file path *\<drive>*:\Certs\Fabrikam Private Encryption.pfx.</span></span>  
  
17. <span data-ttu-id="9c9d1-191">En el **archivo para exportar** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-191">On the **File to Export** page, click **Next**.</span></span>  
  
18. <span data-ttu-id="9c9d1-192">En el **completar el Asistente para exportación de certificados** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-192">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  
  
19. <span data-ttu-id="9c9d1-193">En la ventana emergente de Asistente para exportación de certificados que indica la exportación sea correcta, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-193">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  
  
20. <span data-ttu-id="9c9d1-194">Repita los pasos 10-19 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.pfx privada de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-194">Repeat steps 10-19 for the Fabrikam Signature certificate using the file name Fabrikam Private Signature.pfx.</span></span>  
  
21. <span data-ttu-id="9c9d1-195">Repita los pasos 10-19 de los certificados de firma de Contoso y el cifrado de Contoso con los nombres de archivo Signature.pfx privada de Contoso y Encryption.pfx privada de Contoso, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-195">Repeat steps 10-19 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Private Signature.pfx and Contoso Private Encryption.pfx, respectively.</span></span>  
  
### <a name="to-generate-public-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="9c9d1-196">Para generar los certificados públicos para los certificados de firma y cifrado</span><span class="sxs-lookup"><span data-stu-id="9c9d1-196">To generate public certificates for the Encryption and Signature certificates</span></span>  
  
1.  <span data-ttu-id="9c9d1-197">En la ventana Consola1, expanda **certificados – usuario actual**, expanda **Personal**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-197">In the Console1 window, expand **Certificates – Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
2.  <span data-ttu-id="9c9d1-198">Haga clic en el **Fabrikam cifrado** de certificados, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-198">Right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  
  
3.  <span data-ttu-id="9c9d1-199">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-199">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="9c9d1-200">En el **exportar la clave privada** página, seleccione **No, no exportar la clave privada**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-200">On the **Export Private Key** page, select **No, do not export the private key**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="9c9d1-201">En el **Exportar formato de archivo** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-201">On the **Export File Format** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="9c9d1-202">En el **archivo de exportación** página, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-202">On the **File To Export** page, click **Browse**.</span></span>  
  
7.  <span data-ttu-id="9c9d1-203">En el cuadro de diálogo Guardar como, escriba  **\<unidad >: \Certs** para **guardar en**, **Encryption.cer público de Fabrikam** como **nombre de archivo**, y  **\*.cer** para **Guardar como tipo**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-203">In the Save As dialog box, enter **\<drive>:\Certs** for **Save in**, **Fabrikam Public Encryption.cer** as **File name**, and **\*.cer** for **Save as type**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="9c9d1-204">En el **archivo para exportar** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-204">On the **File to Export** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="9c9d1-205">En el **completar el Asistente para exportación de certificados** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-205">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  
  
10. <span data-ttu-id="9c9d1-206">En la ventana emergente de Asistente para exportación de certificados que indica la exportación sea correcta, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-206">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  
  
11. <span data-ttu-id="9c9d1-207">Repita los pasos del 1 al 9 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.cer pública de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-207">Repeat steps 1-9 for the Fabrikam Signature certificate using the file name Fabrikam Public Signature.cer.</span></span>  
  
12. <span data-ttu-id="9c9d1-208">Repita los pasos del 1 al 9 para los certificados de firma de Contoso y el cifrado de Contoso con los nombres de archivo Signature.cer públicas de Contoso y Contoso Encryption.cer pública, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9c9d1-208">Repeat steps 1-9 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Public Signature.cer and Contoso Public Encryption.cer, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c9d1-209">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c9d1-209">See Also</span></span>  
 [<span data-ttu-id="9c9d1-210">Paso 3: Importar Public y Private certificados</span><span class="sxs-lookup"><span data-stu-id="9c9d1-210">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)