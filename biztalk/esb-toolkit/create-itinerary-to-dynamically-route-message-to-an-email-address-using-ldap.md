---
title: "Cómo: crear un itinerario para dinámicamente enrutar un mensaje a una dirección de correo electrónico mediante una consulta LDAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14ea2f3dcb144b0b3d1ddf835ba3a5ae6a33bb8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a><span data-ttu-id="92596-102">Cómo: crear un itinerario para dinámicamente enrutar un mensaje a una dirección de correo electrónico mediante una consulta LDAP</span><span class="sxs-lookup"><span data-stu-id="92596-102">How to: Create an Itinerary to Dynamically Route a Message to an Email Address Using an LDAP Query</span></span>
## <a name="goal"></a><span data-ttu-id="92596-103">Objetivo</span><span class="sxs-lookup"><span data-stu-id="92596-103">Goal</span></span>  
 <span data-ttu-id="92596-104">En esta sección se muestra cómo crear un itinerario que consulta una dirección de correo electrónico a través de LDAP (Protocolo ligero de acceso a directorios) y, a continuación, envía un mensaje de correo electrónico para el extremo resuelve mediante la [!INCLUDE[prague](../includes/prague-md.md)] adaptador de SMTP.</span><span class="sxs-lookup"><span data-stu-id="92596-104">This section demonstrates how to create an itinerary that queries an e-mail address through LDAP (Lightweight Directory Access Protocol) and then sends an e-mail message to the resolved endpoint using the [!INCLUDE[prague](../includes/prague-md.md)] SMTP adapter.</span></span>  
  
 <span data-ttu-id="92596-105">En este tema "Cómo...", se realizarán los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="92596-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="92596-106">Crear una lista de distribución itinerario para dirigir de manera dinámica un mensaje mediante una consulta LDAP.</span><span class="sxs-lookup"><span data-stu-id="92596-106">Create an itinerary routing slip to dynamically route a message using an LDAP query.</span></span>  
  
-   <span data-ttu-id="92596-107">Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.</span><span class="sxs-lookup"><span data-stu-id="92596-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="92596-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="92596-108">Prerequisites</span></span>  
 <span data-ttu-id="92596-109">Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).</span><span class="sxs-lookup"><span data-stu-id="92596-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
 <span data-ttu-id="92596-110">El equipo en el que se completará esta sección debe tener el servicio de directorio de Microsoft Active Directory configurado y en ejecución (no es necesario que el equipo es el controlador de dominio, pero debe estar conectado al dominio).</span><span class="sxs-lookup"><span data-stu-id="92596-110">The computer on which you will complete this section must have Microsoft Active Directory directory service configured and running (it is not required that the computer is the domain controller, but it must be connected to the domain).</span></span> <span data-ttu-id="92596-111">Además, debe ser un servidor SMTP configurado y en ejecución; Para probar el resultado de este tema "Cómo...", debe tener un cliente con el que se va a comprobar el correo electrónico enviado por ESB.</span><span class="sxs-lookup"><span data-stu-id="92596-111">Also, an SMTP server must be configured and running; in order to test the outcome of this How-to topic, you must have a client with which to check the e-mail sent by the ESB.</span></span>  
  
 <span data-ttu-id="92596-112">Las instrucciones de esta sección presupone una organización denominada Global Bank, con un dominio de globalbank.com, con un Active Directory unidad organizativa denominada a Employees que contiene un usuario denominado a John Evans con una dirección de correo electrónico válida en su perfil (por ejemplo, johne@globalbank.com).</span><span class="sxs-lookup"><span data-stu-id="92596-112">The instructions in this section assume an organization named Global Bank, with a domain of globalbank.com, with an Active Directory Organizational Unit named Employees that contains a user named John Evans with a valid e-mail address in his profile (such as johne@globalbank.com).</span></span> <span data-ttu-id="92596-113">No es necesario replicar estos factores del entorno; Sin embargo, para fines de volver a crear esta implementación en su entorno, tenga en cuenta estos factores y realice las sustituciones según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="92596-113">It is not necessary to replicate these environmental factors; however, for purposes of recreating this implementation in your environment, please account for these factors and make substitutions as necessary.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="92596-114">Pasos</span><span class="sxs-lookup"><span data-stu-id="92596-114">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a><span data-ttu-id="92596-115">Para crear un modelo de lenguaje de específico de dominio (DSL) itinerarios de ESB</span><span class="sxs-lookup"><span data-stu-id="92596-115">To create an ESB itinerary domain-specific language (DSL) model</span></span>  
  
1.  <span data-ttu-id="92596-116">En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.</span><span class="sxs-lookup"><span data-stu-id="92596-116">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="92596-117">En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="92596-117">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="92596-118">En el **Agregar nuevo elemento** cuadro de diálogo, escriba **LdapResolution** en el **nombre** cuadro y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="92596-118">In the **Add New Item** dialog box, type **LdapResolution** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="92596-119">Para configurar las propiedades de la itinerario</span><span class="sxs-lookup"><span data-stu-id="92596-119">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="92596-120">En Visual Studio, haga clic en la superficie de diseño de **LdapResolution.itinerary**.</span><span class="sxs-lookup"><span data-stu-id="92596-120">In Visual Studio, click the design surface of **LdapResolution.itinerary**.</span></span> <span data-ttu-id="92596-121">En el **LdapResolution** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="92596-121">In the **LdapResolution** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="92596-122">En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.</span><span class="sxs-lookup"><span data-stu-id="92596-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="92596-123">En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="92596-123">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="92596-124">En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\LdapResolution** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="92596-124">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\LdapResolution** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="92596-125">Este paso permite exportar el itinerario como XML en una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="92596-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="92596-126">Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB.</span><span class="sxs-lookup"><span data-stu-id="92596-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="92596-127">Complete este proceso más adelante en este tema "Cómo...".</span><span class="sxs-lookup"><span data-stu-id="92596-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="92596-128">Para definir la estructura de la itinerario</span><span class="sxs-lookup"><span data-stu-id="92596-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="92596-129">En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="92596-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="92596-130">En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="92596-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="92596-131">Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.</span><span class="sxs-lookup"><span data-stu-id="92596-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="92596-132">En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="92596-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="92596-133">En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.</span><span class="sxs-lookup"><span data-stu-id="92596-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="92596-134">En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.</span><span class="sxs-lookup"><span data-stu-id="92596-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="92596-135">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="92596-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="92596-136">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="92596-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="92596-137">Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessageEmail**.</span><span class="sxs-lookup"><span data-stu-id="92596-137">Click the **Name** property, and then type **RouteMessageEmail**.</span></span>  
  
    2.  <span data-ttu-id="92596-138">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.</span><span class="sxs-lookup"><span data-stu-id="92596-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="92596-139">Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería).</span><span class="sxs-lookup"><span data-stu-id="92596-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="92596-140">Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="92596-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="92596-141">En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.</span><span class="sxs-lookup"><span data-stu-id="92596-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="92596-142">En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="92596-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="92596-143">Haga clic en el **resolución** colección de la **RouteMessageEmail** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**.</span><span class="sxs-lookup"><span data-stu-id="92596-143">Right-click the **Resolver** collection of the **RouteMessageEmail** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="92596-144">En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="92596-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="92596-145">Haga clic en el **nombre** propiedad y, a continuación, escriba **LdapResolver**.</span><span class="sxs-lookup"><span data-stu-id="92596-145">Click the **Name** property, and then type **LdapResolver**.</span></span>  
  
    2.  <span data-ttu-id="92596-146">En el **implementación de la resolución** la lista desplegable, haga clic en **LDAP resolución extensión**.</span><span class="sxs-lookup"><span data-stu-id="92596-146">In the **Resolver Implementation** drop-down list, click **LDAP Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="92596-147">En el **nombre del transporte** la lista desplegable, haga clic en **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="92596-147">In the **Transport Name** drop-down list, click **SMTP**.</span></span>  
  
    4.  <span data-ttu-id="92596-148">Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **{correo}**</span><span class="sxs-lookup"><span data-stu-id="92596-148">Click the **Transport Location** property, and then type **{mail}**</span></span>  
  
    5.  <span data-ttu-id="92596-149">Haga clic en el **SearchRoot** propiedad y, a continuación, escriba **ou = empleados, dc = globalbank, dc = com**</span><span class="sxs-lookup"><span data-stu-id="92596-149">Click the **SearchRoot** property, and then type **ou=Employees,dc=globalbank,dc=com**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="92596-150">Si no ha configurado el entorno según las especificaciones de la sección "Requisitos previos", reemplace los valores de la propiedad anterior con los que son adecuados para su entorno.</span><span class="sxs-lookup"><span data-stu-id="92596-150">If you have not set up your environment according to the specifications in the "Prerequisites" section, replace the values in the preceding property with ones that are appropriate for your environment.</span></span>  
  
    6.  <span data-ttu-id="92596-151">Haga clic en el **filtro** propiedad y, a continuación, cambie el valor a **(&(objectClass=User) (&#124;(givenName=john)))**</span><span class="sxs-lookup"><span data-stu-id="92596-151">Click the **Filter** property, and then change the value to **(&(objectClass=User)(&#124;(givenName=john)))**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="92596-152">Escriba el valor anterior para reemplazar el texto existente.</span><span class="sxs-lookup"><span data-stu-id="92596-152">Type the preceding value to replace the existing text.</span></span>  
  
    7.  <span data-ttu-id="92596-153">En el **ThrowErrorIfNotFound** la lista desplegable, haga clic en **True**.</span><span class="sxs-lookup"><span data-stu-id="92596-153">In the **ThrowErrorIfNotFound** drop-down list, click **True**.</span></span>  
  
4.  <span data-ttu-id="92596-154">En la ventana Propiedades, haga clic en el **configuración de extremo** propiedad y, a continuación, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="92596-154">In the Properties window, click the **Endpoint Configuration** property, and then click the ellipsis button (...).</span></span>  
  
    1.  <span data-ttu-id="92596-155">En el **configuración de extremo** cuadro de diálogo, haga clic en el **EmailBodyText** propiedad y, a continuación, escriba **orden está listo para ser procesado**.</span><span class="sxs-lookup"><span data-stu-id="92596-155">In the **Endpoint Configuration** dialog box, click the **EmailBodyText** property, and then type **Order is ready to be processed**.</span></span>  
  
    2.  <span data-ttu-id="92596-156">Haga clic en el **de** propiedad y, a continuación, escriba  **orders@globalbank.com** .</span><span class="sxs-lookup"><span data-stu-id="92596-156">Click the **From** property, and then type **orders@globalbank.com**.</span></span>  
  
    3.  <span data-ttu-id="92596-157">Haga clic en el **MessagePartsAttachment** propiedad y, a continuación, escriba **2**.</span><span class="sxs-lookup"><span data-stu-id="92596-157">Click the **MessagePartsAttachment** property, and then type **2**.</span></span>  
  
    4.  <span data-ttu-id="92596-158">Haga clic en el **asunto** propiedad y, a continuación, escriba **orden para {givenName}**.</span><span class="sxs-lookup"><span data-stu-id="92596-158">Click the **Subject** property, and then type **Order for {givenName}**.</span></span>  
  
    5.  <span data-ttu-id="92596-159">Configurar la **SMTPAuthentication, SMTPHost, nombre de usuario,** y **contraseña** propiedades mediante la información de conexión para su entorno local.</span><span class="sxs-lookup"><span data-stu-id="92596-159">Configure the **SMTPAuthentication, SMTPHost, UserName,** and **Password** properties using the connection information for your local environment.</span></span>  
  
    6.  <span data-ttu-id="92596-160">Haga clic en **Aceptar** para cerrar el **configuración de extremo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="92596-160">Click **OK** to close the **Endpoint Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="92596-161">Haga clic en el **LdapResolver** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.</span><span class="sxs-lookup"><span data-stu-id="92596-161">Right-click the **LdapResolver** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
6.  <span data-ttu-id="92596-162">En la ventana de salida, compruebe el sujeto en el que se resuelven **configuración de extremo** valor es **orden John**y, a continuación, compruebe que el resuelto **transporte ubicación** es el asociado a la cuenta del usuario en Active Directory de dirección de correo electrónico (por ejemplo, johne@globalbank.com).</span><span class="sxs-lookup"><span data-stu-id="92596-162">In the Output window, verify the subject in the resolved **Endpoint Configuration** value is **Order for John**, and then verify that the resolved **Transport Location** is the e-mail address associated with the user's account in Active Directory (for example, johne@globalbank.com).</span></span>  
  
7.  <span data-ttu-id="92596-163">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="92596-163">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="92596-164">Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessageEmail** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="92596-164">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessageEmail** model element.</span></span>  
  
8.  <span data-ttu-id="92596-165">En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteMessageEmail** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="92596-165">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteMessageEmail** model element.</span></span> <span data-ttu-id="92596-166">En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="92596-166">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="92596-167">Haga clic en el **nombre** propiedad y, a continuación, escriba **EmailNAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="92596-167">Click the **Name** property, and then type **EmailNAOrderDoc**.</span></span>  
  
    2.  <span data-ttu-id="92596-168">En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.</span><span class="sxs-lookup"><span data-stu-id="92596-168">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="92596-169">En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.</span><span class="sxs-lookup"><span data-stu-id="92596-169">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="92596-170">En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.</span><span class="sxs-lookup"><span data-stu-id="92596-170">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
9. <span data-ttu-id="92596-171">En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteMessageEmail** elemento del modelo y la **EmailNAOrderDoc**elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="92596-171">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteMessageEmail** model element and the **EmailNAOrderDoc** model element.</span></span> <span data-ttu-id="92596-172">En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="92596-172">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="92596-173">Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.</span><span class="sxs-lookup"><span data-stu-id="92596-173">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="92596-174">En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.</span><span class="sxs-lookup"><span data-stu-id="92596-174">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="92596-175">En el **fuera de rampa** lista desplegable lista, expanda **EmailNAOrderDoc**y, a continuación, haga clic en **controladores de envío**.</span><span class="sxs-lookup"><span data-stu-id="92596-175">In the **Off-Ramp** drop-down list, expand **EmailNAOrderDoc**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="92596-176">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="92596-176">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="92596-177">Arrastre una conexión desde el **RouteMessageEmail** elemento de modelo para el **SendPortFilter** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="92596-177">Drag a connection from the **RouteMessageEmail** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="92596-178">En el cuadro de herramientas, haga clic en **conector**.</span><span class="sxs-lookup"><span data-stu-id="92596-178">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="92596-179">Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **EmailNAOrderDoc** elemento del modelo.</span><span class="sxs-lookup"><span data-stu-id="92596-179">Drag a connection from the **SendPortFilter** model element to the **EmailNAOrderDoc** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="92596-180">Para exportar el modelo para su uso con el cliente de prueba de itinerario</span><span class="sxs-lookup"><span data-stu-id="92596-180">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="92596-181">En Visual Studio, haga clic en la superficie de diseño de la **LdapResolution** itinerario y, a continuación, haga clic en **Exportar modelo**.</span><span class="sxs-lookup"><span data-stu-id="92596-181">In Visual Studio, right-click the design surface of the **LdapResolution** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92596-182">La versión XML del itinerario se abre en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="92596-182">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="92596-183">Guarde todos los artefactos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="92596-183">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="92596-184">En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (LdapResolution.xml).</span><span class="sxs-lookup"><span data-stu-id="92596-184">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (LdapResolution.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="92596-185">Para probar el itinerario</span><span class="sxs-lookup"><span data-stu-id="92596-185">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="92596-186">Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).</span><span class="sxs-lookup"><span data-stu-id="92596-186">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="92596-187">En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.</span><span class="sxs-lookup"><span data-stu-id="92596-187">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="92596-188">En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries.</span><span class="sxs-lookup"><span data-stu-id="92596-188">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="92596-189">Seleccione **LdapResolution.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.</span><span class="sxs-lookup"><span data-stu-id="92596-189">Select **LdapResolution.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="92596-190">Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.</span><span class="sxs-lookup"><span data-stu-id="92596-190">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="92596-191">En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.</span><span class="sxs-lookup"><span data-stu-id="92596-191">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="92596-192">En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="92596-192">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="92596-193">Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.</span><span class="sxs-lookup"><span data-stu-id="92596-193">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="92596-194">Haga clic en el **Submit Request** botón.</span><span class="sxs-lookup"><span data-stu-id="92596-194">Click the **Submit Request** button.</span></span> <span data-ttu-id="92596-195">Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="92596-195">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="92596-196">Abra Microsoft Outlook Express (o el cliente de correo electrónico de su elección) y comprobar la entrega del mensaje al correo electrónico de John Evans.</span><span class="sxs-lookup"><span data-stu-id="92596-196">Open Microsoft Outlook Express (or the mail client of your choice) and verify delivery of the message to the e-mail of John Evans.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="92596-197">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="92596-197">Additional Resources</span></span>  
 <span data-ttu-id="92596-198">Para obtener más información, vea los siguientes temas relacionados:</span><span class="sxs-lookup"><span data-stu-id="92596-198">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="92596-199">Actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="92596-199">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="92596-200">Uso de resolución dinámica y enrutamiento</span><span class="sxs-lookup"><span data-stu-id="92596-200">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)