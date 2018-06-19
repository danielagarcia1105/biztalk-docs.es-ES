---
title: 'Paso 1: Crear una entidad de certificación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, creating
- double action tutorial, creating certificates
- creating, certificates
ms.assetid: b6ecd534-6b03-4336-8337-33ec18a0802a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d796608a4cc323ccf5e1a8bdee7420c5bab259
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966234"
---
# <a name="step-1-creating-a-certification-authority"></a><span data-ttu-id="401ba-102">Paso 1: Crear una entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="401ba-102">Step 1: Creating a Certification Authority</span></span>
<span data-ttu-id="401ba-103">En este tema, instale los servicios de Certificate Server [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] componente.</span><span class="sxs-lookup"><span data-stu-id="401ba-103">In this topic, you install the Certificate Services [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] component.</span></span> <span data-ttu-id="401ba-104">Usarlo para generar los certificados que necesita para promover una comunicación segura entre las organizaciones de Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="401ba-104">You use it to generate the certificates that you need to promote secure communication between the Contoso and Fabrikam organizations.</span></span> <span data-ttu-id="401ba-105">Todos los socios comerciales tendrá un certificado de cifrado privada para la comunicación y el certificado de firma privada para propósitos de identificación.</span><span class="sxs-lookup"><span data-stu-id="401ba-105">Each trading partner will have a private encryption certificate for communication and a private signature certificate for identification purposes.</span></span> <span data-ttu-id="401ba-106">Además, los socios compartirán sus certificados de clave pública entre sí para promover una comunicación segura al implementar el proceso de interfaz de socio (PIP) 3A2.</span><span class="sxs-lookup"><span data-stu-id="401ba-106">Additionally, the partners will share their public key certificates with each other to promote secure communication when implementing the 3A2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-install-the-certificate-server"></a><span data-ttu-id="401ba-107">Para instalar al servidor de certificados</span><span class="sxs-lookup"><span data-stu-id="401ba-107">To install the certificate server</span></span>  
  
1.  <span data-ttu-id="401ba-108">Haga clic en **iniciar**, seleccione **configuración**y, a continuación, haga clic en **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="401ba-108">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span> <span data-ttu-id="401ba-109">Haga doble clic en **agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="401ba-109">Double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="401ba-110">En el **agregar o quitar programas** cuadro de diálogo, haga clic en **agregar o quitar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="401ba-110">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="401ba-111">En el **Asistente para componentes de Windows** página, en la **componentes** sección, seleccione **servicios de Certificate Server**, haga clic en **Sí**y, a continuación, haga clic en **Siguiente** para iniciar el Asistente para la configuración de componentes.</span><span class="sxs-lookup"><span data-stu-id="401ba-111">On the **Windows Components Wizard** page, in the **Components** section, select **Certificate Services**, click **Yes**, and then click **Next** to start the Configuring Components Wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="401ba-112">Si el **ServicesWindows certificados** componente ya está seleccionado, omita el resto de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="401ba-112">If the **Certificates ServicesWindows** component is already selected, skip the rest of this procedure.</span></span>  
  
4.  <span data-ttu-id="401ba-113">En el **el tipo de CA** página, asegúrese de que **entidad emisora raíz independiente** está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-113">On the **CA Type** page, make sure that **Stand-alone root CA** is selected, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="401ba-114">En el **información de identificación de la entidad emisora de certificados** página, en la **nombre común para esta entidad de certificación** , escriba **Contoso FabrikamCA**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-114">On the **CA Identifying Information** page, in the **Common name for this CA** box, type **Contoso-FabrikamCA**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="401ba-115">En el **configuración de base de datos de certificados** página, deje los valores predeterminados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-115">On the **Certificate Database Settings** page, leave the defaults, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="401ba-116">Haga clic en **Sí** cuando el asistente le pregunta si desea detener los servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="401ba-116">Click **Yes** when the wizard prompts you to stop Internet Information Services (IIS).</span></span>  
  
8.  <span data-ttu-id="401ba-117">Haga clic en **Sí** si la **Asistente para componentes de la configuración** le solicita que habilite las páginas Active Server.</span><span class="sxs-lookup"><span data-stu-id="401ba-117">Click **Yes** if the **Configuring Components Wizard** prompts you to enable Active Server Pages.</span></span>  
  
9. <span data-ttu-id="401ba-118">Haga clic en **finalizar** para cerrar el **Asistente para componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="401ba-118">Click **Finish** to close the **Windows Components Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="401ba-119">Solamente debe usar un equipo como la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="401ba-119">You only have to use one computer as the Certification Authority.</span></span> <span data-ttu-id="401ba-120">No es necesario repetir este paso en el segundo equipo.</span><span class="sxs-lookup"><span data-stu-id="401ba-120">You do not have to repeat this step on the second computer.</span></span> <span data-ttu-id="401ba-121">Este tutorial usa el equipo de Contoso como la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="401ba-121">This tutorial uses the Contoso computer as the Certification Authority.</span></span>  
  
### <a name="to-install-a-root-certification-authority-ca-for-windows-server-2008"></a><span data-ttu-id="401ba-122">Para instalar una entidad de certificación (CA) raíz de Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="401ba-122">To install a root Certification Authority (CA) for Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="401ba-123">Abra Administrador del servidor, haga clic en **agregar Roles** en Roles, haga clic en **siguiente**y haga clic en **certificados de Active Directory** casilla de verificación de servicios.</span><span class="sxs-lookup"><span data-stu-id="401ba-123">Open Server Manager, click **Add Roles** in Roles, click **Next**, and click **Active Directory Certificate** Services check box.</span></span> <span data-ttu-id="401ba-124">Haga clic en **siguiente** dos veces.</span><span class="sxs-lookup"><span data-stu-id="401ba-124">Click **Next** twice.</span></span>  
  
2.  <span data-ttu-id="401ba-125">En la página Seleccionar servicios de rol, haga clic en **entidad emisora de certificados y la inscripción Web de entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="401ba-125">On the Select Role Services page, click **Certification Authority and Certification Authority Web Enrollment**.</span></span> <span data-ttu-id="401ba-126">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-126">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="401ba-127">En la página Especificar tipo de instalación, haga clic en **independiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-127">On the Specify Setup Type page, click **Standalone**.</span></span> <span data-ttu-id="401ba-128">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-128">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="401ba-129">En la página especificar el tipo de entidad emisora de certificados, haga clic en la entidad de certificación raíz.</span><span class="sxs-lookup"><span data-stu-id="401ba-129">On the Specify CA Type page, click Root CA.</span></span> <span data-ttu-id="401ba-130">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-130">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="401ba-131">En la página Configurar clave privada, haga clic en crear una nueva clave privada.</span><span class="sxs-lookup"><span data-stu-id="401ba-131">On the Set Up Private Key page, click Create a new private key.</span></span> <span data-ttu-id="401ba-132">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="401ba-133">En la criptografía configurar para la página de la entidad emisora de certificados.</span><span class="sxs-lookup"><span data-stu-id="401ba-133">On the Configure Cryptography for CA page.</span></span> <span data-ttu-id="401ba-134">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-134">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="401ba-135">Configurar el nombre de entidad emisora de certificados, en el cuadro Nombre común para esta entidad emisora de certificados, escriba Contoso FabrikamCA y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-135">On Configure CA Name, in the Common name for this CA box, type Contoso-FabrikamCA, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="401ba-136">En la página establecer el período de validez, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-136">On the Set Validity Period page, click **Next**.</span></span>  
  
9. <span data-ttu-id="401ba-137">En la página Configurar base de datos de certificados, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="401ba-137">On the Configure Certificate Database page, Click **Next**.</span></span>  
  
10. <span data-ttu-id="401ba-138">En la página Confirmar opciones de instalación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="401ba-138">On the Confirm Installation Options page, click **Install**.</span></span>  
  
### <a name="configuring-the-web-site-for-the-ca-to-use-https-authentication"></a><span data-ttu-id="401ba-139">Configurar el sitio Web de la CA para que use autenticación HTTPS</span><span class="sxs-lookup"><span data-stu-id="401ba-139">Configuring the Web site for the CA to use HTTPS authentication</span></span>  
  
1.  <span data-ttu-id="401ba-140">En el equipo en el que se utiliza como la entidad de certificación, haga clic en Inicio, seleccione todos los programas, herramientas administrativas y, a continuación, haga clic en Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="401ba-140">On the computer you used as the Certification Authority, click Start, point to All Programs, point to Administrative Tools, and then click Internet Information Services (IIS) Manager.</span></span>  
  
2.  <span data-ttu-id="401ba-141">En el cuadro de diálogo Administrador de Internet Information Services (IIS), haga clic en **sitio Web predeterminado y seleccione Modificar enlaces...**</span><span class="sxs-lookup"><span data-stu-id="401ba-141">In the Internet Information Services (IIS) Manager dialog box, right click **Default Web Site and select Edit Bindings…**</span></span> <span data-ttu-id="401ba-142">en el menú emergente.</span><span class="sxs-lookup"><span data-stu-id="401ba-142">from the popup menu.</span></span>  
  
3.  <span data-ttu-id="401ba-143">En el cuadro de diálogo de enlaces de sitios, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="401ba-143">In Site Bindings dialog box click **Add**.</span></span>  
  
4.  <span data-ttu-id="401ba-144">En el cuadro de diálogo Agregar enlace de sitio seleccione **https** en la lista desplegable Tipo, seleccione el certificado de **certificado SSL** de lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="401ba-144">In Add Site Binding dialog box select **https** in Type drop down, select the certificate from **SSL certificate** drop down and click **OK**.</span></span>  
  
5.  <span data-ttu-id="401ba-145">Haga clic en **cerrar** para cerrar los enlaces de sitio...</span><span class="sxs-lookup"><span data-stu-id="401ba-145">Click **Close** to close the Site Bindings…</span></span> <span data-ttu-id="401ba-146">cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="401ba-146">dialog box.</span></span>  
  
### <a name="to-download-the-ca-certificate"></a><span data-ttu-id="401ba-147">Para descargar el certificado de CA</span><span class="sxs-lookup"><span data-stu-id="401ba-147">To download the CA certificate</span></span>  
  
1.  <span data-ttu-id="401ba-148">En Internet Explorer, busque y abra http://<contoso_computername>/certsrv/Default.asp.</span><span class="sxs-lookup"><span data-stu-id="401ba-148">In Internet Explorer, locate and open http://<contoso_computername>/certsrv/Default.asp.</span></span>  
  
2.  <span data-ttu-id="401ba-149">En la página Default.asp, haga clic en **descargar un certificado de CA, cadena de certificados o CRL**.</span><span class="sxs-lookup"><span data-stu-id="401ba-149">On the Default.asp page, click **Download a CA certificate, certificate chain, or CRL**.</span></span>  
  
3.  <span data-ttu-id="401ba-150">Asegúrese de que **actual [Contoso-FabrikamCA]** está seleccionado en el **certificado de CA** lista y, a continuación, haga clic en **Descargar certificado de entidad emisora de certificados**.</span><span class="sxs-lookup"><span data-stu-id="401ba-150">Make sure that **Current[Contoso-FabrikamCA]** is selected in the **CA Certificate** list, and then click **Download CA Certificate**.</span></span>  
  
4.  <span data-ttu-id="401ba-151">Guarde el certificado en C:\Certs\Contoso-FabrikamCA.cer en el de Contoso y el equipo de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="401ba-151">Save the certificate to C:\Certs\Contoso-FabrikamCA.cer on both the Contoso and the Fabrikam computer.</span></span>  
  
### <a name="to-import-the-ca-certificate-to-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="401ba-152">Para importar el certificado de CA en el almacén de entidades de certificación raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="401ba-152">To import the CA certificate to the Trusted Root Certification Authorities store</span></span>  
  
1.  <span data-ttu-id="401ba-153">Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="401ba-153">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="401ba-154">En el símbolo del sistema, vaya a  **\<unidad\>: \Program Files\MicrosoftBizTalk \<versión\> Accelerator for RosettaNet\SDK**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="401ba-154">At the command prompt, move to **\<drive\>:\Program Files\MicrosoftBizTalk \<version\> Accelerator for RosettaNet\SDK**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="401ba-155">En el símbolo del sistema, escriba **CertWizard /Rootkey "\<unidad\>: \Certs\Contoso-FabrikamCA.cer"** y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="401ba-155">At the command prompt, type **CertWizard /Rootkey "\<drive\>:\Certs\Contoso-FabrikamCA.cer"**, and then press **Enter**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="401ba-156">Llevar a cabo este procedimiento en los equipos de Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="401ba-156">Perform this procedure on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-enable-automatic-certificate-issuing"></a><span data-ttu-id="401ba-157">Para habilitar la emisión automática de certificados</span><span class="sxs-lookup"><span data-stu-id="401ba-157">To enable automatic certificate issuing</span></span>  
  
1.  <span data-ttu-id="401ba-158">En el equipo en el que se utiliza como la entidad de certificación, haga clic en **iniciar**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en  **Entidad de certificación**.</span><span class="sxs-lookup"><span data-stu-id="401ba-158">On the computer you used as the Certification Authority, click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="401ba-159">En el cuadro de diálogo entidad de certificación, haga clic en **Contoso FabrikamCA**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="401ba-159">In the Certification Authority dialog box, right-click **Contoso-FabrikamCA**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="401ba-160">En el cuadro de diálogo Propiedades de Contoso-FabrikamCA, en la **módulo de directivas** , haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="401ba-160">In the Contoso-FabrikamCA Properties dialog box, on the **Policy Module** tab, click **Properties**.</span></span>  
  
4.  <span data-ttu-id="401ba-161">En el cuadro de diálogo Propiedades, seleccione **seguir la configuración de la plantilla de certificado**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="401ba-161">In the Properties dialog box, select **Follow the settings in the certificate template**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="401ba-162">Haga clic en **Aceptar** para cerrar el cuadro de diálogo FabrikamCA de Contoso.</span><span class="sxs-lookup"><span data-stu-id="401ba-162">Click **OK** to close the Contoso-FabrikamCA dialog box.</span></span>  
  
6.  <span data-ttu-id="401ba-163">Cierre el cuadro de diálogo de la entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="401ba-163">Close the Certification Authority dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="401ba-164">Al habilitar la emisión de certificados automática, servicios de Certificate Server automatiza el procedimiento de emisión de certificados.</span><span class="sxs-lookup"><span data-stu-id="401ba-164">By enabling automatic certificate issuing, Certificate Services automates the certificate issuing procedure.</span></span> <span data-ttu-id="401ba-165">Tendrá que reiniciar los servicios de Certificate Server para aplicar este cambio.</span><span class="sxs-lookup"><span data-stu-id="401ba-165">You will have to restart Certificate Services to apply this change.</span></span>  
    >   
    >  <span data-ttu-id="401ba-166">Debe instalar el certificado raíz Contoso-FabrikamCA.cer en las entidades de certificación de raíz de User\Trusted actual.</span><span class="sxs-lookup"><span data-stu-id="401ba-166">You may need to install the Root Certificate Contoso-FabrikamCA.cer in the Current User\Trusted Root Certification authorities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401ba-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="401ba-167">See Also</span></span>  
 [<span data-ttu-id="401ba-168">Paso 2: Crear certificados públicos y privados</span><span class="sxs-lookup"><span data-stu-id="401ba-168">Step 2: Creating Public and Private Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)