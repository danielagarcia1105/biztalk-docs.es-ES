---
title: 'Paso 2: Creación de certificados públicos y privados | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating certificates
- public certificates
- certificates, public certificates
- creating, certificates
- private certificates
ms.assetid: 0a925d89-03d9-41fe-907b-85a6ae42362a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f31d1bb1dcc5a0e6f587797f41e97d16ca6606da
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007613"
---
# <a name="step-2-creating-public-and-private-certificates"></a><span data-ttu-id="45912-102">Paso 2: Creación de certificados públicos y privados</span><span class="sxs-lookup"><span data-stu-id="45912-102">Step 2: Creating Public and Private Certificates</span></span>
<span data-ttu-id="45912-103">En este paso, usará la entidad de certificación que se creó en [paso 1: creación de una entidad de certificación &#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) para generar los certificados públicos y privados que utilizan las organizaciones de Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="45912-103">In this step, you use the Certification Authority created in [Step 1: Creating a Certification Authority &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md) to generate the public and private certificates that the Contoso and Fabrikam organizations use.</span></span>  

### <a name="to-generate-the-contoso-and-fabrikam-encryption-certificates"></a><span data-ttu-id="45912-104">Para generar los certificados de cifrado de Contoso y Fabrikam</span><span class="sxs-lookup"><span data-stu-id="45912-104">To generate the Contoso and Fabrikam encryption certificates</span></span>  

1. <span data-ttu-id="45912-105">En el equipo que utiliza como la entidad de certificación en Internet Explorer, busque y abra http://<contoso_computername>/certsrv.</span><span class="sxs-lookup"><span data-stu-id="45912-105">On the computer you used as the Certification Authority, in Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  

2. <span data-ttu-id="45912-106">En el **bienvenida** página, haga clic en **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="45912-106">On the **Welcome** page, click **Request a certificate**.</span></span>  

3. <span data-ttu-id="45912-107">En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.</span><span class="sxs-lookup"><span data-stu-id="45912-107">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  

4. <span data-ttu-id="45912-108">En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="45912-108">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  

5. <span data-ttu-id="45912-109">En el **solicitud de certificado avanzada** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45912-109">On the **Advanced Certificate Request** page, do the following:</span></span>  


   |            <span data-ttu-id="45912-110">Use</span><span class="sxs-lookup"><span data-stu-id="45912-110">Use this</span></span>            |                                                                         <span data-ttu-id="45912-111">Para</span><span class="sxs-lookup"><span data-stu-id="45912-111">To do this</span></span>                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            <span data-ttu-id="45912-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="45912-112">**Name**</span></span>            |                                                               <span data-ttu-id="45912-113">Tipo **Fabrikam cifrado**.</span><span class="sxs-lookup"><span data-stu-id="45912-113">Type **Fabrikam Encryption**.</span></span>                                                                |
   |           <span data-ttu-id="45912-114">**Correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="45912-114">**E-Mail**</span></span>           |                                                          <span data-ttu-id="45912-115">Tipo <strong>jdoe@fabrikam.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="45912-115">Type <strong>jdoe@fabrikam.com</strong>.</span></span>                                                          |
   |          <span data-ttu-id="45912-116">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="45912-116">**Company**</span></span>           |                                                                     <span data-ttu-id="45912-117">Tipo **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="45912-117">Type **Fabrikam**.</span></span>                                                                     |
   |         <span data-ttu-id="45912-118">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="45912-118">**Department**</span></span>         |                                                                       <span data-ttu-id="45912-119">Tipo **prueba**.</span><span class="sxs-lookup"><span data-stu-id="45912-119">Type **Test**.</span></span>                                                                       |
   |            <span data-ttu-id="45912-120">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="45912-120">**City**</span></span>            |                                                                       <span data-ttu-id="45912-121">Tipo **prueba**.</span><span class="sxs-lookup"><span data-stu-id="45912-121">Type **Test**.</span></span>                                                                       |
   |           <span data-ttu-id="45912-122">**State**</span><span class="sxs-lookup"><span data-stu-id="45912-122">**State**</span></span>            |                                                                       <span data-ttu-id="45912-123">Tipo **prueba**.</span><span class="sxs-lookup"><span data-stu-id="45912-123">Type **Test**.</span></span>                                                                       |
   |       <span data-ttu-id="45912-124">**País o región**</span><span class="sxs-lookup"><span data-stu-id="45912-124">**Country/Region**</span></span>       |                                                                        <span data-ttu-id="45912-125">Tipo **US**.</span><span class="sxs-lookup"><span data-stu-id="45912-125">Type **US**.</span></span>                                                                        |
   | <span data-ttu-id="45912-126">**Tipo de certificado necesario**</span><span class="sxs-lookup"><span data-stu-id="45912-126">**Type of Certificate Needed**</span></span> |                                             <span data-ttu-id="45912-127">Seleccione **certificado de protección de correo electrónico** desde la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="45912-127">Select **E-Mail Protection Certificate** from the drop down list.</span></span>                                              |
   |         <span data-ttu-id="45912-128">**Uso de claves**</span><span class="sxs-lookup"><span data-stu-id="45912-128">**Key Usage**</span></span>          |                                                              <span data-ttu-id="45912-129">Seleccione el **Exchange** opción.</span><span class="sxs-lookup"><span data-stu-id="45912-129">Select the **Exchange** option.</span></span>                                                               |
   |   <span data-ttu-id="45912-130">**Opciones adicionales de clave**</span><span class="sxs-lookup"><span data-stu-id="45912-130">**Additional Key Options**</span></span>   | <span data-ttu-id="45912-131">Coloque una marca de verificación en las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="45912-131">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="45912-132">-   **Marcar esta clave como exportable**</span><span class="sxs-lookup"><span data-stu-id="45912-132">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="45912-133">-   **Store certificado en el almacén de certificados equipo local**</span><span class="sxs-lookup"><span data-stu-id="45912-133">-   **Store certificate in the local computer certificate store**</span></span> |
   |       <span data-ttu-id="45912-134">**Nombre descriptivo**</span><span class="sxs-lookup"><span data-stu-id="45912-134">**Friendly Name**</span></span>        |                                                               <span data-ttu-id="45912-135">Tipo **Fabrikam cifrado**.</span><span class="sxs-lookup"><span data-stu-id="45912-135">Type **Fabrikam Encryption**.</span></span>                                                                |


6. <span data-ttu-id="45912-136">Haga clic en **enviar**y, a continuación, haga clic en **Sí** en **confirmación del acceso Web** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="45912-136">Click **Submit**, and then click **Yes** in **Web Access Confirmation** dialog box.</span></span>  

7. <span data-ttu-id="45912-137">En el **certificado emitido** página, haga clic en **instalar este certificado**.</span><span class="sxs-lookup"><span data-stu-id="45912-137">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  

8. <span data-ttu-id="45912-138">Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación del** sección y la **Nombre_descriptivo** cuadro a **Contoso Cifrado**.</span><span class="sxs-lookup"><span data-stu-id="45912-138">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Encryption**.</span></span>  

### <a name="to-generate-the-contoso-and-fabrikam-signing-certificates"></a><span data-ttu-id="45912-139">Para generar los Contoso y Fabrikam certificados de firma</span><span class="sxs-lookup"><span data-stu-id="45912-139">To generate the Contoso and Fabrikam Signing Certificates</span></span>  

1. <span data-ttu-id="45912-140">En Internet Explorer, busque y abra http://<contoso_computername>/certsrv.</span><span class="sxs-lookup"><span data-stu-id="45912-140">In Internet Explorer, locate and open http://<contoso_computername>/certsrv.</span></span>  

2. <span data-ttu-id="45912-141">En el **bienvenida** página, haga clic en **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="45912-141">On the **Welcome** page, click **Request a certificate**.</span></span>  

3. <span data-ttu-id="45912-142">En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.</span><span class="sxs-lookup"><span data-stu-id="45912-142">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  

4. <span data-ttu-id="45912-143">En el **solicitud de certificado avanzada** página, haga clic en **crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="45912-143">On the **Advanced Certificate Request** page, click **Create and submit a request to this CA**.</span></span>  

5. <span data-ttu-id="45912-144">En el **solicitud de certificado avanzada** página, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45912-144">On the **Advanced Certificate Request** page, do the following:</span></span>  


   |            <span data-ttu-id="45912-145">Use</span><span class="sxs-lookup"><span data-stu-id="45912-145">Use this</span></span>            |                                                                         <span data-ttu-id="45912-146">Para</span><span class="sxs-lookup"><span data-stu-id="45912-146">To do this</span></span>                                                                         |
   |--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |            <span data-ttu-id="45912-147">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="45912-147">**Name**</span></span>            |                                                                <span data-ttu-id="45912-148">Tipo **Fabrikam firma**.</span><span class="sxs-lookup"><span data-stu-id="45912-148">Type **Fabrikam Signature**.</span></span>                                                                |
   |           <span data-ttu-id="45912-149">**Correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="45912-149">**E-Mail**</span></span>           |                                                          <span data-ttu-id="45912-150">Tipo <strong>jdoe@fabrikam.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="45912-150">Type <strong>jdoe@fabrikam.com</strong>.</span></span>                                                          |
   |          <span data-ttu-id="45912-151">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="45912-151">**Company**</span></span>           |                                                                     <span data-ttu-id="45912-152">Tipo **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="45912-152">Type **Fabrikam**.</span></span>                                                                     |
   |         <span data-ttu-id="45912-153">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="45912-153">**Department**</span></span>         |                                                                       <span data-ttu-id="45912-154">Tipo **prueba**.</span><span class="sxs-lookup"><span data-stu-id="45912-154">Type **Test**.</span></span>                                                                       |
   |            <span data-ttu-id="45912-155">**Ciudad**</span><span class="sxs-lookup"><span data-stu-id="45912-155">**City**</span></span>            |                                                                       <span data-ttu-id="45912-156">Tipo **prueba**.</span><span class="sxs-lookup"><span data-stu-id="45912-156">Type **Test**.</span></span>                                                                       |
   |           <span data-ttu-id="45912-157">**State**</span><span class="sxs-lookup"><span data-stu-id="45912-157">**State**</span></span>            |                                                                       <span data-ttu-id="45912-158">Tipo **prueba**.</span><span class="sxs-lookup"><span data-stu-id="45912-158">Type **Test**.</span></span>                                                                       |
   |       <span data-ttu-id="45912-159">**País o región**</span><span class="sxs-lookup"><span data-stu-id="45912-159">**Country/Region**</span></span>       |                                                                        <span data-ttu-id="45912-160">Tipo **US**.</span><span class="sxs-lookup"><span data-stu-id="45912-160">Type **US**.</span></span>                                                                        |
   | <span data-ttu-id="45912-161">**Tipo de certificado necesario**</span><span class="sxs-lookup"><span data-stu-id="45912-161">**Type of Certificate Needed**</span></span> |                                             <span data-ttu-id="45912-162">Seleccione **certificado de protección de correo electrónico**.de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="45912-162">Select **E-Mail Protection Certificate**.from the drop down list.</span></span>                                              |
   |         <span data-ttu-id="45912-163">**Uso de claves**</span><span class="sxs-lookup"><span data-stu-id="45912-163">**Key Usage**</span></span>          |                                                              <span data-ttu-id="45912-164">Seleccione el **firma** opción.</span><span class="sxs-lookup"><span data-stu-id="45912-164">Select the **Signature** option.</span></span>                                                              |
   |   <span data-ttu-id="45912-165">**Opciones adicionales de clave**</span><span class="sxs-lookup"><span data-stu-id="45912-165">**Additional Key Options**</span></span>   | <span data-ttu-id="45912-166">Coloque una marca de verificación en las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="45912-166">Place a check in the following options:</span></span><br /><br /> <span data-ttu-id="45912-167">-   **Marcar esta clave como exportable**</span><span class="sxs-lookup"><span data-stu-id="45912-167">-   **Mark keys as exportable**</span></span><br /><span data-ttu-id="45912-168">-   **Store certificado en el almacén de certificados equipo local**</span><span class="sxs-lookup"><span data-stu-id="45912-168">-   **Store certificate in the local computer certificate store**</span></span> |
   |       <span data-ttu-id="45912-169">**Nombre descriptivo**</span><span class="sxs-lookup"><span data-stu-id="45912-169">**Friendly Name**</span></span>        |                                                                <span data-ttu-id="45912-170">Tipo **Fabrikam firma**.</span><span class="sxs-lookup"><span data-stu-id="45912-170">Type **Fabrikam Signature**.</span></span>                                                                |


6. <span data-ttu-id="45912-171">Haga clic en **enviar**y, a continuación, haga clic en **Sí** cuando se le pida para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="45912-171">Click **Submit**, and then click **Yes** when asked to request the certificate.</span></span>  

7. <span data-ttu-id="45912-172">En el **certificado emitido** página, haga clic en **instalar este certificado**.</span><span class="sxs-lookup"><span data-stu-id="45912-172">On the **Certificate Issued** page, click **Install this certificate**.</span></span>  

8. <span data-ttu-id="45912-173">Repita los pasos 1-7, cambiar la información de la **nombre** cuadro el **información de identificación del** sección y la **Nombre_descriptivo** cuadro a **Contoso Firma**.</span><span class="sxs-lookup"><span data-stu-id="45912-173">Repeat steps 1-7, changing the information in the **Name** box in the **Identifying Information** section and the **Friendly Name** box to **Contoso Signature**.</span></span>  

### <a name="to-generate-private-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="45912-174">Para generar certificados privados para los certificados de cifrado y firma</span><span class="sxs-lookup"><span data-stu-id="45912-174">To generate private certificates for the Encryption and Signature certificates</span></span>  

1.  <span data-ttu-id="45912-175">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **MMC**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="45912-175">Click **Start**, click **Run**, type **MMC**, and then click **OK**.</span></span>  

2.  <span data-ttu-id="45912-176">En la ventana Consola1, en el **archivo** menú, haga clic en **agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="45912-176">In the Console1 window, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  

3.  <span data-ttu-id="45912-177">En el cuadro de diálogo Agregar o quitar complemento, en el **independiente** , haga clic **agregar**.</span><span class="sxs-lookup"><span data-stu-id="45912-177">In the Add/Remove Snap-in dialog box, on the **Standalone** tab, click **Add**.</span></span>  

4.  <span data-ttu-id="45912-178">En el cuadro de diálogo Add Standalone Snap-in, seleccione el **certificados** complemento desde la **complementos Standalone disponibles** lista y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="45912-178">In the Add Standalone Snap-in dialog box, select the **Certificates** snap-in from the **Available Standalone Snap-ins** list, and then click **Add**.</span></span>  

5.  <span data-ttu-id="45912-179">En el cuadro de diálogo complemento de certificados, seleccione **mi cuenta de usuario**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-179">In the Certificates snap-in dialog box, select **My user account**, and then click **Next**.</span></span>  

6.  <span data-ttu-id="45912-180">En el cuadro de diálogo Seleccionar equipo, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="45912-180">In the Select Computer dialog box, click **Finish**.</span></span>  

7.  <span data-ttu-id="45912-181">En el cuadro de diálogo Add Standalone Snap-in, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="45912-181">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  

8.  <span data-ttu-id="45912-182">En el cuadro de diálogo Agregar o quitar complemento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="45912-182">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  

9. <span data-ttu-id="45912-183">En la ventana Consola1, expanda **certificados (equipo Local)**, expanda **Personal**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="45912-183">In the Console1 window, expand **Certificates (Local Computer)**, expand **Personal**, and then click **Certificates**.</span></span>  

10. <span data-ttu-id="45912-184">En el panel derecho, haga clic en el **Fabrikam cifrado** de certificado, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="45912-184">In the right pane, right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  

11. <span data-ttu-id="45912-185">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-185">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  

12. <span data-ttu-id="45912-186">En el **exportar la clave privada** página, seleccione **Sí, exportar la clave privada**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-186">On the **Export Private Key** page, select **Yes, export the private key**, and then click **Next**.</span></span>  

13. <span data-ttu-id="45912-187">En el **Exportar formato de archivo** página, asegúrese de que **Personal Information Exchange** es la única opción seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-187">On the **Export File Format** page, make sure that **Personal Information Exchange** is the only option selected, and then click **Next**.</span></span>  

14. <span data-ttu-id="45912-188">En el **contraseña** página, en el **contraseña** y **Confirmar contraseña** cuadros, escriba **MiSecreto**y, a continuación, haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="45912-188">On the **Password** page, in the **Password** and **Confirm Password** boxes, type **mysecret**, and then click **Next**.</span></span>  

15. <span data-ttu-id="45912-189">En el **archivo de exportación** página, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="45912-189">On the **File To Export** page, click **Browse**.</span></span>  

16. <span data-ttu-id="45912-190">En el **Guardar como** cuadro de diálogo, guarde el certificado con la ruta de acceso de archivo  *\<unidad\>*: \Certs\Fabrikam Encryption.pfx privada.</span><span class="sxs-lookup"><span data-stu-id="45912-190">In the **Save As** dialog box, save the certificate using the file path *\<drive\>*:\Certs\Fabrikam Private Encryption.pfx.</span></span>  

17. <span data-ttu-id="45912-191">En el **archivo para exportar** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-191">On the **File to Export** page, click **Next**.</span></span>  

18. <span data-ttu-id="45912-192">En el **completar el Asistente para exportar certificados** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="45912-192">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  

19. <span data-ttu-id="45912-193">En el menú emergente de Asistente para exportar certificados que indica una exportación correcta, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="45912-193">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  

20. <span data-ttu-id="45912-194">Repita los pasos 10-19 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.pfx privada de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="45912-194">Repeat steps 10-19 for the Fabrikam Signature certificate using the file name Fabrikam Private Signature.pfx.</span></span>  

21. <span data-ttu-id="45912-195">Repita los pasos 10-19 para los certificados de firma de Contoso y el cifrado de Contoso mediante los nombres de archivo Signature.pfx privado de Contoso y Encryption.pfx privado de Contoso, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="45912-195">Repeat steps 10-19 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Private Signature.pfx and Contoso Private Encryption.pfx, respectively.</span></span>  

### <a name="to-generate-public-certificates-for-the-encryption-and-signature-certificates"></a><span data-ttu-id="45912-196">Para generar certificados públicos para los certificados de cifrado y firma</span><span class="sxs-lookup"><span data-stu-id="45912-196">To generate public certificates for the Encryption and Signature certificates</span></span>  

1.  <span data-ttu-id="45912-197">En la ventana Consola1, expanda **certificados – usuario actual**, expanda **Personal**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="45912-197">In the Console1 window, expand **Certificates – Current User**, expand **Personal**, and then click **Certificates**.</span></span>  

2.  <span data-ttu-id="45912-198">Haga clic en el **Fabrikam cifrado** de certificado, seleccione **todas las tareas**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="45912-198">Right-click the **Fabrikam Encryption** certificate, point to **All Tasks**, and then click **Export**.</span></span>  

3.  <span data-ttu-id="45912-199">En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-199">On the **Welcome to the Certificate Export Wizard** page, click **Next**.</span></span>  

4.  <span data-ttu-id="45912-200">En el **exportar la clave privada** página, seleccione **No, no exportar la clave privada**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-200">On the **Export Private Key** page, select **No, do not export the private key**, and then click **Next**.</span></span>  

5.  <span data-ttu-id="45912-201">En el **Exportar formato de archivo** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-201">On the **Export File Format** page, click **Next**.</span></span>  

6.  <span data-ttu-id="45912-202">En el **archivo de exportación** página, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="45912-202">On the **File To Export** page, click **Browse**.</span></span>  

7.  <span data-ttu-id="45912-203">En el cuadro de diálogo Guardar como, escriba  **\<unidad\>: \Certs** para **guardar en**, **Fabrikam pública Encryption.cer** como **nombre de archivo** , y  **\*.cer** para **Guardar como tipo**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="45912-203">In the Save As dialog box, enter **\<drive\>:\Certs** for **Save in**, **Fabrikam Public Encryption.cer** as **File name**, and **\*.cer** for **Save as type**, and then click **Save**.</span></span>  

8.  <span data-ttu-id="45912-204">En el **archivo para exportar** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45912-204">On the **File to Export** page, click **Next**.</span></span>  

9. <span data-ttu-id="45912-205">En el **completar el Asistente para exportar certificados** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="45912-205">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span>  

10. <span data-ttu-id="45912-206">En el menú emergente de Asistente para exportar certificados que indica una exportación correcta, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="45912-206">In the Certificate Export Wizard popup indicating a successful export, click **OK**.</span></span>  

11. <span data-ttu-id="45912-207">Repita los pasos 1 a 9 para el certificado de firma de Fabrikam mediante el nombre de archivo Signature.cer pública de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="45912-207">Repeat steps 1-9 for the Fabrikam Signature certificate using the file name Fabrikam Public Signature.cer.</span></span>  

12. <span data-ttu-id="45912-208">Repita los pasos 1 a 9 para los certificados de firma de Contoso y el cifrado de Contoso mediante los nombres de archivo Signature.cer público de Contoso y Encryption.cer público de Contoso, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="45912-208">Repeat steps 1-9 for the Contoso Signature and Contoso Encryption certificates using the file names Contoso Public Signature.cer and Contoso Public Encryption.cer, respectively.</span></span>  

## <a name="see-also"></a><span data-ttu-id="45912-209">Vea también</span><span class="sxs-lookup"><span data-stu-id="45912-209">See Also</span></span>  
 [<span data-ttu-id="45912-210">Paso 3: Importar certificados públicos y privados</span><span class="sxs-lookup"><span data-stu-id="45912-210">Step 3: Importing Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)