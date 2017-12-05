---
title: 'Paso 4: Habilitar SSL en IIS | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Secure Socket Layers
- IIS
- double action tutorial, enabling SSL in IIS
- SSL
ms.assetid: 96109294-595a-46ac-974e-33123df79ed5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2964b6ac26d6685a1c38b88c5bbf98e8119f3502
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-enabling-secure-sockets-layer-in-iis"></a><span data-ttu-id="bb63b-102">Paso 4: Habilitar SSL en IIS</span><span class="sxs-lookup"><span data-stu-id="bb63b-102">Step 4: Enabling Secure Sockets Layer in IIS</span></span>
<span data-ttu-id="bb63b-103">Capa de Sockets seguros (SSL) es un protocolo que se han diseñado para proteger el canal de comunicación entre un cliente y un servidor.</span><span class="sxs-lookup"><span data-stu-id="bb63b-103">Secure Sockets Layer (SSL) is a protocol designed to secure the communication channel between a client and a server.</span></span> <span data-ttu-id="bb63b-104">Al habilitar SSL en Microsoft® Internet Information Services (IIS) 7.5 o 7.0, las organizaciones de Contoso y Fabrikam comunican mediante autenticación y cifrado para todas las transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="bb63b-104">By enabling SSL in Microsoft® Internet Information Services (IIS) 7.5/7.0, the Contoso and Fabrikam organizations communicate using authentication and encryption for all data transfers.</span></span> <span data-ttu-id="bb63b-105">En este paso, obtener información sobre cómo habilitar SSL en IIS 7.5 o 7.0.</span><span class="sxs-lookup"><span data-stu-id="bb63b-105">In this step, you learn how to enable SSL in IIS 7.5/7.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb63b-106">Tendrá que realizar este paso en los equipos de Contoso y Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="bb63b-106">You have to perform this step on both the Contoso and Fabrikam computers.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate"></a><span data-ttu-id="bb63b-107">Para preparar un nuevo certificado de servidor</span><span class="sxs-lookup"><span data-stu-id="bb63b-107">To prepare a new server certificate</span></span>  
  
1.  <span data-ttu-id="bb63b-108">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="bb63b-109">En el panel izquierdo de Internet Information Services, expanda  **\<**  *computer_name*  **\>**  (*ordenador*), expanda **sitios Web**, haga clic en **sitio Web predeterminado**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-109">In the Internet Information Services left pane, expand **\<***computer_name***\>** (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="bb63b-110">En el cuadro de diálogo de sitios Web predeterminados en la **seguridad de directorios** , haga clic en **certificado de servidor** para iniciar el **Asistente para certificados IIS**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-110">In the Default Web Sites dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4.  <span data-ttu-id="bb63b-111">En el **éste es el Asistente para certificados de servidor Web** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-111">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="bb63b-112">En el **certificado de servidor** página, seleccione **crear un nuevo certificado**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-112">On the **Server Certificate** page, select **Create a new certificate**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="bb63b-113">En el **Petición demorada o inmediata** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-113">On the **Delayed or immediate request** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="bb63b-114">En el **nombre y la configuración de seguridad** página, haga clic en **siguiente**, mantener los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bb63b-114">On the **Name and Security Settings** page, click **Next**, keeping the defaults.</span></span>  
  
8.  <span data-ttu-id="bb63b-115">En el **información de la organización** página, en la **organización** , escriba **Contoso** if en el equipo de Contoso o **Fabrikam** if en la Equipo de Fabrikam, en la **unidad organizativa** , escriba **prueba**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-115">On the **Organization Information** page, in the **Organization** box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the **Organizational unit** box, type **Test**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="bb63b-116">En el **nombre común de su sitio Web** página, en la **nombre común** , escriba el nombre del equipo y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-116">On the **Your Site's Common Name** page, in the **Common name** box, type the name of your computer, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="bb63b-117">En el **información geográfica** página, en la **estado/provincia** , escriba su estado o provincia, en la **ciudad o localidad** , escriba la ciudad o localidad y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-117">On the **Geographical Information** page, in the **State/province** box, type your state/province, in the **City/locality** box, type your city/locality, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="bb63b-118">En el **nombre de archivo de solicitud de certificado** página, en la **nombre de archivo** cuadro, deje el valor predeterminado **C:\certreq.txt**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-118">On the **Certificate Request File Name** page, in the **File name** box, leave the default **C:\certreq.txt**, and then click **Next**.</span></span>  
  
12. <span data-ttu-id="bb63b-119">En el **resumen del archivo de petición** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-119">On the **Request File Summary** page, click **Next**.</span></span>  
  
13. <span data-ttu-id="bb63b-120">En el **completar el Asistente para certificados de servidor Web** página, haga clic en **finalizar** para cerrar el **Asistente para certificados IIS**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-120">On the **Completing the Web Server Certificate Wizard** page, click **Finish** to close the **IIS Certificate Wizard**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate"></a><span data-ttu-id="bb63b-121">Para generar un nuevo certificado de servidor</span><span class="sxs-lookup"><span data-stu-id="bb63b-121">To generate a new server certificate</span></span>  
  
1.  <span data-ttu-id="bb63b-122">En Internet Explorer, busque y abra http://\<*contoso_machine* \> /certsrv.</span><span class="sxs-lookup"><span data-stu-id="bb63b-122">In Internet Explorer, locate and open http://\<*contoso_machine*\>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb63b-123">En el paso 1, abra http://\<*contoso_machine* \> /certsrv en el equipo de Contoso o Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="bb63b-123">In step 1, open http://\<*contoso_machine*\>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="bb63b-124">En el **principal del Asistente para Microsoft Certificate Services** página, haga clic en **solicitar un certificado.**</span><span class="sxs-lookup"><span data-stu-id="bb63b-124">On the **Microsoft Certificate Services Wizard Welcome** page, click **Request a certificate.**</span></span>  
  
3.  <span data-ttu-id="bb63b-125">En el **solicitar un certificado** página, haga clic en **solicitud de certificado avanzada**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-125">On the **Request a Certificate** page, click **advanced certificate request**.</span></span>  
  
4.  <span data-ttu-id="bb63b-126">En el **solicitud de certificado avanzada** página, haga clic en **enviar una solicitud de certificado mediante un archivo CMC o PKCS #10 codificado en base-64, o enviar una solicitud de renovación mediante un archivo PKCS #7 codificado en base 64**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-126">On the **Advanced Certificate Request** page, click **Submit a certificate request by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file**.</span></span>  
  
5.  <span data-ttu-id="bb63b-127">En el **enviar una solicitud de certificado o una solicitud de renovación** página, haga clic en **buscar un archivo insertar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-127">On the **Submit a Certificate Request or Renewal Request** page, click **Browse for a file to insert**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb63b-128">Si recibe un error de seguridad al hacer clic en el vínculo, abra el archivo C:\certreq.txt en el Bloc de notas u otro editor de texto, copie el contenido del archivo y pegue esa información en el **Guardar solicitud** cuadro y, a continuación, haga clic en  **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-128">If you receive a security error when clicking the link, open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box, and then click **Submit**.</span></span> <span data-ttu-id="bb63b-129">A continuación, puede ir al paso 10.</span><span class="sxs-lookup"><span data-stu-id="bb63b-129">You can then go to step 10.</span></span>  
  
6.  <span data-ttu-id="bb63b-130">Haga clic en **examinar** para abrir el **Elegir archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb63b-130">Click **Browse** to open the **Choose File** dialog box.</span></span>  
  
7.  <span data-ttu-id="bb63b-131">En el **Elegir archivo** diálogo cuadro, busque la  *\<unidad\>*: \ carpeta, seleccione el archivo certreq.txt y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-131">In the **Choose File** dialog box, locate the *\<drive\>*:\ folder, select the certreq.txt file, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="bb63b-132">En el **enviar una solicitud de certificado o una solicitud de renovación** página, haga clic en **lectura**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-132">On the **Submit a Certificate Request or Renewal Request** page, click **Read**.</span></span>  
  
9. <span data-ttu-id="bb63b-133">En el **enviar una solicitud de certificado o una solicitud de renovación** página, haga clic en **Submit** para generar el nuevo certificado.</span><span class="sxs-lookup"><span data-stu-id="bb63b-133">On the **Submit a Certificate Request or Renewal Request** page, click **Submit** to generate the new certificate.</span></span>  
  
10. <span data-ttu-id="bb63b-134">En el **certificado emitido** página, haga clic en **Descargar certificado**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-134">On the **Certificate Issued** page, click **Download Certificate**.</span></span>  
  
11. <span data-ttu-id="bb63b-135">En el **descarga de archivos** cuadro de diálogo, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-135">In the **File Download** dialog box, click **Save**.</span></span>  
  
12. <span data-ttu-id="bb63b-136">En el **Guardar como** cuadro de diálogo, guarde el certificado a \<unidad\>: \Certs\SSLCert.cer y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-136">In the **Save As** dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="bb63b-137">Haga clic en **cerrar** para cerrar el **descarga completa** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb63b-137">Click **Close** to close the **Download Complete** dialog box.</span></span>  
  
### <a name="to-prepare-a-new-server-certificate-for-iis"></a><span data-ttu-id="bb63b-138">Para preparar un nuevo certificado de servidor para IIS</span><span class="sxs-lookup"><span data-stu-id="bb63b-138">To Prepare a new Server Certificate for IIS</span></span>  
  
1.  <span data-ttu-id="bb63b-139">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-139">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="bb63b-140">En el panel izquierdo de Internet Information Services, haga clic en < nombre_equipo > (equipo local), haga doble clic en **certificados de servidor** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="bb63b-140">In the Internet Information Services left pane, click <computer_name> (local computer), double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="bb63b-141">Seleccione **crear solicitud de certificado** desde el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="bb63b-141">Select **Create Certificate Request** from Actions pane.</span></span>  
  
3.  <span data-ttu-id="bb63b-142">En el cuadro de diálogo Propiedades de nombre distintivo, escriba el nombre del equipo en el nombre común: cuadro de texto, en la organización:, escriba **Contoso** if en el equipo de Contoso o **Fabrikam** if en Fabrikam equipo en la unidad organizativa: tipo de prueba, en el cuadro ciudad o localidad, escriba su ciudad o localidad, en el cuadro de estado o provincia, escriba su estado o provincia, en el país o región desplegable, seleccione su país/región y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-142">In Distinguished Name Properties dialog box type the name of the computer in the Common name: text box, in the Organization: box, type **Contoso** if on the Contoso computer or **Fabrikam** if on the Fabrikam computer, in the Organizational unit: box type Test, in the City/locality box, type your city/locality, in the State/province box, type your state/province, in the Country/region drop down, select your Country/region and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="bb63b-143">En el cuadro de diálogo Propiedades del proveedor de servicios criptográficos, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-143">In the Cryptographic Service Provider Properties dialog box, click **Next**.</span></span>  
  
5.  <span data-ttu-id="bb63b-144">En el cuadro de diálogo Nombre de archivo, especifique C:\certreq.txt en el cuadro de texto, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-144">In the File Name dialog box, specify C:\certreq.txt in the text box, click **Finish**.</span></span>  
  
### <a name="to-generate-a-new-server-certificate-for-iis"></a><span data-ttu-id="bb63b-145">Para generar un nuevo certificado de servidor para IIS</span><span class="sxs-lookup"><span data-stu-id="bb63b-145">To generate a new server certificate for IIS</span></span>  
  
1.  <span data-ttu-id="bb63b-146">En Internet Explorer, busque y abra http://<contoso_machine>/CertSrv.</span><span class="sxs-lookup"><span data-stu-id="bb63b-146">In Internet Explorer, locate and open http://<contoso_machine>/CertSrv.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb63b-147">En el paso 1, abra http://<contoso_machine>/CertSrv en el equipo de Contoso o Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="bb63b-147">In step 1, open http://<contoso_machine>/CertSrv on the Contoso or Fabrikam computer.</span></span>  
  
2.  <span data-ttu-id="bb63b-148">En la página de bienvenida del Asistente para Microsoft Certificate Services, haga clic en **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-148">On the Microsoft Certificate Services Wizard Welcome page, click **Request a certificate**.</span></span>  
  
3.  <span data-ttu-id="bb63b-149">En la página solicitar un certificado, haga clic en **solicitud de certificado avanzada**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-149">On the Request a Certificate page, click **Advanced Certificate Request**.</span></span>  
  
4.  <span data-ttu-id="bb63b-150">En la página de solicitud de certificado avanzada, haga clic en **enviar una solicitud de certificado** por mediante un archivo CMC o PKCS #10 codificado en base-64, o enviar una solicitud de renovación mediante un archivo PKCS #7 codificado en base 64.</span><span class="sxs-lookup"><span data-stu-id="bb63b-150">On the Advanced Certificate Request page, click **Submit a certificate request** by using a base-64-encoded CMC or PKCS #10 file, or submit a renewal request by using a base-64-encoded PKCS #7 file.</span></span>  
  
5.  <span data-ttu-id="bb63b-151">Abra el archivo C:\certreq.txt en el Bloc de notas u otro editor de texto, copie el contenido del archivo y pegue esa información en el **Guardar solicitud** cuadro al enviar una página de solicitud de certificado o la solicitud de renovación y, a continuación, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-151">Open the file C:\certreq.txt in Notepad or another text editor, copy the contents of the file and paste that information in the **Saved Request** box on the Submit a Certificate Request or Renewal Request page, and then click **Submit**.</span></span>  
  
6.  <span data-ttu-id="bb63b-152">En la página certificado emitido, haga clic en **Descargar certificado**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-152">On the Certificate Issued page, click **Download Certificate**.</span></span>  
  
7.  <span data-ttu-id="bb63b-153">En el cuadro de diálogo descarga de archivos, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-153">In the File Download dialog box, click **Save**.</span></span>  
  
8.  <span data-ttu-id="bb63b-154">En el cuadro de diálogo Guardar como, guardar el certificado \<unidad\>: \Certs\SSLCert.cer y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-154">In the Save As dialog box, save the certificate to \<drive\>:\Certs\SSLCert.cer, and then click **Save**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="bb63b-155">Para importar el certificado de servidor en IIS</span><span class="sxs-lookup"><span data-stu-id="bb63b-155">To import the server certificate into IIS</span></span>  
  
1.  <span data-ttu-id="bb63b-156">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-156">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="bb63b-157">En el panel izquierdo de Internet Information Services, haga clic en **(equipo local)**, haga doble clic en **certificados de servidor** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="bb63b-157">In the Internet Information Services left pane, click **(local computer)**, double click **Server Certificates** in the right pane.</span></span> <span data-ttu-id="bb63b-158">Seleccione **solicitud de certificado completo** en el panel Acciones.</span><span class="sxs-lookup"><span data-stu-id="bb63b-158">Select **Complete Certificate Request** from the Actions pane.</span></span>  
  
3.  <span data-ttu-id="bb63b-159">En el tipo de cuadro de diálogo Especificar respuesta de la entidad emisora de certificados  **\<unidad\>: \Certs\SSLCert.cer** en **nombre de archivo que contiene la respuesta de la entidad de certificación** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bb63b-159">In Specify Certificate Authority Response dialog box type **\<drive\>:\Certs\SSLCert.cer** in **File name containing the certification authority’s response** text box.</span></span> <span data-ttu-id="bb63b-160">En el tipo de cuadro de texto Nombre descriptivo **ContosoSSLCert**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-160">In Friendly name text box type **ContosoSSLCert**.</span></span>  
  
### <a name="to-enable-ssl-bindings-for-iis"></a><span data-ttu-id="bb63b-161">Para permitir a los enlaces de SSL para IIS</span><span class="sxs-lookup"><span data-stu-id="bb63b-161">To enable SSL bindings for IIS</span></span>  
  
1.  <span data-ttu-id="bb63b-162">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-162">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="bb63b-163">En el panel izquierdo de Internet Information Services, expanda **(equipo local)**, expanda **sitios**, haga clic en **sitio Web predeterminado**y, a continuación, haga clic en **editar Enlaces**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-163">In the Internet Information Services left pane, expand **(local computer)**, expand **Sites**, right-click **Default Web Site**, and then click **Edit Bindings**.</span></span>  
  
3.  <span data-ttu-id="bb63b-164">En el cuadro de diálogo de enlaces de sitios, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-164">In Site Bindings dialog box click **Add**.</span></span> <span data-ttu-id="bb63b-165">En el cuadro de diálogo Agregar enlace de sitio seleccione **https** en la lista desplegable Tipo, seleccione **ContosoSSLCert** en SSL certificado desplegable, haga clic en **Aceptar**, haga clic en **cerrar** .</span><span class="sxs-lookup"><span data-stu-id="bb63b-165">In the Add Site Binding dialog box select **https** from Type drop down, select **ContosoSSLCert** from SSL certificate drop down, click **OK**, click **Close**.</span></span>  
  
### <a name="to-import-the-server-certificate-into-iis"></a><span data-ttu-id="bb63b-166">Para importar el certificado de servidor en IIS</span><span class="sxs-lookup"><span data-stu-id="bb63b-166">To import the server certificate into IIS</span></span>  
  
1.  <span data-ttu-id="bb63b-167">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-167">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="bb63b-168">En el panel izquierdo de Internet Information Services, expanda  **\<**  *computer_name* \> (*equipo local*), expanda **Web Sitios**, haga clic en **sitio Web predeterminado**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-168">In the Internet Information Services left pane, expand **\<***computer_name*\> (*local computer*), expand **Web Sites**, right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="bb63b-169">En el cuadro de diálogo Propiedades del sitio Web predeterminado, en la **seguridad de directorios** , haga clic en **certificado de servidor** para iniciar el **Asistente para certificados IIS**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-169">In the Default Web Site Properties dialog box, on the **Directory Security** tab, click **Server Certificate** to start the **IIS Certificate Wizard**.</span></span>  
  
4.  <span data-ttu-id="bb63b-170">En el **éste es el Asistente para certificados de servidor Web** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-170">On the **Welcome to the Web Server Certificate Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="bb63b-171">En el **solicitud de certificado pendiente** página, seleccione **procesar la petición pendiente e instalar el certificado**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-171">On the **Pending Certificate Request** page, select **Process the pending request and install the certificate**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="bb63b-172">En el **procesar una solicitud pendiente** página, en la **ruta de acceso y nombre de archivo** , escriba  **\<unidad\>: \Certs\SSLCert.cer** (o vaya a ese archivo) y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-172">On the **Process a Pending Request** page, in the **Path and file name** box, type **\<drive\>:\Certs\SSLCert.cer** (or browse to that file) and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="bb63b-173">En el **página puerto SSL**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-173">On the **SSL Port page**, click **Next**.</span></span>  
  
8.  <span data-ttu-id="bb63b-174">En el **resumen del certificado** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-174">On the **Certificate Summary** page, click **Next**.</span></span>  
  
9. <span data-ttu-id="bb63b-175">En el **completar el Asistente para certificados de servidor Web** página, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb63b-175">On the **Completing the Web Server Certificate Wizard** page, click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb63b-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb63b-176">See Also</span></span>  
 [<span data-ttu-id="bb63b-177">Creación y configuración de la solución de Contoso</span><span class="sxs-lookup"><span data-stu-id="bb63b-177">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)