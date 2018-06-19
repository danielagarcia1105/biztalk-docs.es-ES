---
title: Solución de problemas de SharePoint Services adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f88174-118d-4ed6-8449-c89ca195ce5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9885696df24cd5c5f8321ad3c6dd79d444559a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280236"
---
# <a name="troubleshooting-sharepoint-services-adapter"></a><span data-ttu-id="e2eab-102">Solución de problemas del adaptador de SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="e2eab-102">Troubleshooting SharePoint Services Adapter</span></span>
<span data-ttu-id="e2eab-103">Este tema está centrado en la resolución de problemas con el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS).</span><span class="sxs-lookup"><span data-stu-id="e2eab-103">This topic focuses on troubleshooting the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) adapter.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="e2eab-104">Installation</span><span class="sxs-lookup"><span data-stu-id="e2eab-104">Installation</span></span>  
 <span data-ttu-id="e2eab-105">Cuando utilice el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS), tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="e2eab-105">When using the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) adapter, there are two options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2eab-106">**Usar el modelo de objetos cliente** establecido en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e2eab-106">**Use Client OM** set to **Yes**.</span></span>|<span data-ttu-id="e2eab-107">**Se recomienda**.</span><span class="sxs-lookup"><span data-stu-id="e2eab-107">**Recommended**.</span></span> <span data-ttu-id="e2eab-108">Cuando se establece en Sí, se utiliza el modelo de objetos cliente (CSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2eab-108">When set to Yes, the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM) is used.</span></span> <span data-ttu-id="e2eab-109">El adaptador se instala con la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2eab-109">The adapter is installed when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span> <span data-ttu-id="e2eab-110">No es necesario ningún paso de instalación adicional.</span><span class="sxs-lookup"><span data-stu-id="e2eab-110">There are no additional installation steps.</span></span> <span data-ttu-id="e2eab-111">**Nota:** el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación también instala automáticamente el cliente objeto modelo SharePoint redistribuible disponible en [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span><span class="sxs-lookup"><span data-stu-id="e2eab-111">**Note:**  The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation also automatically installs the SharePoint Client Object Model Redistributable available at [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span></span>|  
|<span data-ttu-id="e2eab-112">**Usar el modelo de objetos cliente** establecido en **No**.</span><span class="sxs-lookup"><span data-stu-id="e2eab-112">**Use Client OM** set to **No**.</span></span>|<span data-ttu-id="e2eab-113">**Opción obsoleta**.</span><span class="sxs-lookup"><span data-stu-id="e2eab-113">**Deprecated**.</span></span> <span data-ttu-id="e2eab-114">Con esta opción, se utiliza el modelo de objetos cliente de servicio (SSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2eab-114">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span><br /><br /> <span data-ttu-id="e2eab-115">y se instala un servicio web en el equipo de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], que puede ser el mismo equipo de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] u otro distinto.</span><span class="sxs-lookup"><span data-stu-id="e2eab-115">A web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span><br /><br /> <span data-ttu-id="e2eab-116">Para instalar el servicio web, ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación en el [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] equipo y compruebe **adaptador de Windows SharePoint Services**.</span><span class="sxs-lookup"><span data-stu-id="e2eab-116">To install the web service, run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer and check **Windows SharePoint Services Adapter**.</span></span> <span data-ttu-id="e2eab-117">Vea [Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) de pasos de instalación específicos.</span><span class="sxs-lookup"><span data-stu-id="e2eab-117">See [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) for specific installation steps.</span></span>|  
  
 <span data-ttu-id="e2eab-118">**Usar el modelo de objetos cliente** establecido en **Sí** se recomienda.</span><span class="sxs-lookup"><span data-stu-id="e2eab-118">**Use Client OM** set to **Yes** is recommended.</span></span> <span data-ttu-id="e2eab-119">Cuando se establece en **Sí**, el servicio web no está instalado en el equipo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e2eab-119">When set to **Yes**, the web service is NOT installed on the SharePoint computer.</span></span> <span data-ttu-id="e2eab-120">Si prefiere usar la opción de servicio web, debe establecer **utilizar modelo de objetos de cliente** a **No** en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2eab-120">If you prefer to use the web service option, you must set **Use Client OM** to **No** on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="iis"></a><span data-ttu-id="e2eab-121">IIS</span><span class="sxs-lookup"><span data-stu-id="e2eab-121">IIS</span></span>  
 <span data-ttu-id="e2eab-122">**Servicio web BTSharePointAdapterWS.asmx**</span><span class="sxs-lookup"><span data-stu-id="e2eab-122">**BTSharePointAdapterWS.asmx web service**</span></span>  
  
 <span data-ttu-id="e2eab-123">Cuando se instala el adaptador de [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] en el equipo de SharePoint, se crea el servicio web BTSharePointAdapterWS.asmx en IIS en el equipo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e2eab-123">When the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter is installed on the SharePoint computer, the BTSharePointAdapterWS.asmx web service is created in IIS on the SharePoint computer.</span></span> <span data-ttu-id="e2eab-124">Por lo general, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SharePoint están instalados en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="e2eab-124">Typically, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SharePoint are installed on different computers.</span></span> <span data-ttu-id="e2eab-125">Al instalar SharePoint, la base de datos SQL de contenido puede ser local del equipo de SharePoint o puede encontrarse en una versión de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] remota.</span><span class="sxs-lookup"><span data-stu-id="e2eab-125">When SharePoint is installed, the content SQL database can be local to the SharePoint computer or on a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e2eab-126">**Grupo de aplicaciones usa la cuenta de dominio**</span><span class="sxs-lookup"><span data-stu-id="e2eab-126">**Application Pool uses Domain account**</span></span>  
  
 <span data-ttu-id="e2eab-127">Cuando BizTalk y SharePoint se encuentran en equipos distintos, el grupo de aplicaciones IIS que ejecute el servicio web BTSharePointAdapterWS.asmx debe utilizar una cuenta de dominio..</span><span class="sxs-lookup"><span data-stu-id="e2eab-127">When BizTalk and SharePoint are on different computers, the IIS application pool running the BTSharePointAdapterWS.asmx web service must use a domain account.</span></span> <span data-ttu-id="e2eab-128">En caso de que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las bases de datos de BizTalk, [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] y las bases de datos de SharePoint de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] estén instalados en el mismo equipo, es posible utilizar una cuenta local.</span><span class="sxs-lookup"><span data-stu-id="e2eab-128">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the BizTalk databases, [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint databases are all installed on the same computer, then a local account can be used.</span></span>  
  
 <span data-ttu-id="e2eab-129">**Escenario de salto doble**</span><span class="sxs-lookup"><span data-stu-id="e2eab-129">**Double-Hop Scenario**</span></span>  
  
 <span data-ttu-id="e2eab-130">Cuando el proceso implica a tres equipos ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]), se crea un escenario de salto doble que requiere autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="e2eab-130">When there are three computers involved ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]), there is a double-hop scenario that requires Kerberos authentication.</span></span> <span data-ttu-id="e2eab-131">El adaptador de SharePoint del equipo de BizTalk realiza una solicitud POST al servicio web BTSharePointAdapterWS.asmx en el equipo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e2eab-131">The SharePoint adapter on the BizTalk computer does a POST request to the BTSharePointAdapterWS.asmx web service on the SharePoint computer.</span></span> <span data-ttu-id="e2eab-132">A continuación, el equipo de SharePoint consulta su base de datos en el equipo de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2eab-132">The SharePoint computer then queries its databases on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
 <span data-ttu-id="e2eab-133">Esta solicitud POST del adaptador de BizTalk debe completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="e2eab-133">This POST request from the BizTalk adapter must complete successfully.</span></span> <span data-ttu-id="e2eab-134">Si sospecha que existe algún error de autenticación, revise los registros de IIS.</span><span class="sxs-lookup"><span data-stu-id="e2eab-134">If you suspect an authentication failure, review the IIS logs.</span></span> <span data-ttu-id="e2eab-135">De forma predeterminada, los registros de IIS se encuentran en c:\inetpub\logs\LogFiles\W3SVC*x*.</span><span class="sxs-lookup"><span data-stu-id="e2eab-135">By default, the IIS logs are in c:\inetpub\logs\LogFiles\W3SVC*x*.</span></span> <span data-ttu-id="e2eab-136">La solicitud POST debe mostrar el código de estado 200 (operación llevada a cabo correctamente).</span><span class="sxs-lookup"><span data-stu-id="e2eab-136">The POST request should display a 200 (success) status code.</span></span> <span data-ttu-id="e2eab-137">Si se devuelve un código de estado de error, como un 401.2, seguido por un 401.1, seguido de otro 4*xx* errores y, a continuación, la autenticación puede no ser correcta.</span><span class="sxs-lookup"><span data-stu-id="e2eab-137">If a failed status code is returned, like a 401.2, followed by a 401.1, following by another 4*xx* error, then authentication may be failing.</span></span>  
  
 <span data-ttu-id="e2eab-138">Cuando se utilice la autenticación Kerberos, es necesario utilizar los nombres principales de servicio (SPN) y debe habilitarse la delegación.</span><span class="sxs-lookup"><span data-stu-id="e2eab-138">When Kerberos authentication is used, service principal names (SPN) are required and delegation must be enabled.</span></span>  
  
## <a name="enable-kerberos-authentication"></a><span data-ttu-id="e2eab-139">Habilitar la autenticación Kerberos</span><span class="sxs-lookup"><span data-stu-id="e2eab-139">Enable Kerberos Authentication</span></span>  
 <span data-ttu-id="e2eab-140">En un escenario de salto doble, es necesario utilizar la autenticación Kerberos y habilitar la delegación.</span><span class="sxs-lookup"><span data-stu-id="e2eab-140">In a double-hop scenario, Kerberos authentication and enabling delegation are required.</span></span> <span data-ttu-id="e2eab-141">Entre los pasos necesarios se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2eab-141">Steps include:</span></span>  
  
1.  <span data-ttu-id="e2eab-142">Habilitar **Negotiate** en el servidor IIS/SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e2eab-142">Enable **Negotiate** on the IIS/SharePoint server.</span></span> <span data-ttu-id="e2eab-143">[215383: cómo configurar IIS para que admita el protocolo Kerberos y el protocolo NTLM para la autenticación de red](http://support.microsoft.com/kb/215383) se enumeran los pasos.</span><span class="sxs-lookup"><span data-stu-id="e2eab-143">[215383: How to configure IIS to support both the Kerberos protocol and the NTLM protocol for network authentication](http://support.microsoft.com/kb/215383) lists the steps.</span></span>  
  
2.  <span data-ttu-id="e2eab-144">Los nombres principales de servicio (SPN) son necesarios para las cuentas de dominio que ejecuten el servicio [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y el Grupo de aplicaciones en el equipo de IIS/SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e2eab-144">Service Principal Names (SPNs) are required for the domain accounts executing the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Service and the Application Pool on the IIS/SharePoint computer.</span></span> <span data-ttu-id="e2eab-145">Para crear un SPN, utilice la herramienta de línea de comandos SetSPN.exe:</span><span class="sxs-lookup"><span data-stu-id="e2eab-145">To create an SPN, use the SetSPN.exe command-line tool:</span></span>  
  
     [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]<span data-ttu-id="e2eab-146">: [Hay disponible una actualización para Setspn.exe en Windows Server 2003](http://support.microsoft.com/kb/970536)</span><span class="sxs-lookup"><span data-stu-id="e2eab-146">: [An update for Setspn.exe in Windows Server 2003 is available](http://support.microsoft.com/kb/970536)</span></span>  
  
     [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]<span data-ttu-id="e2eab-147">8, [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2eab-147"> 8, [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e2eab-148">SetSPN requiere derechos de administrador del dominio y puede ejecutarse desde cualquier equipo del dominio.</span><span class="sxs-lookup"><span data-stu-id="e2eab-148">SetSPN requires Domain Administrator rights and can be executed from any computer in the domain.</span></span>  
  
     <span data-ttu-id="e2eab-149">Para devolver una lista de todos los SPN registrados en una cuenta de dominio:</span><span class="sxs-lookup"><span data-stu-id="e2eab-149">To return a list of all SPNs registered to a domain account:</span></span>  
  
    ```  
    setspn.exe -l Domain\UserAccount  
    ```  
  
     <span data-ttu-id="e2eab-150">Cree los SPN:</span><span class="sxs-lookup"><span data-stu-id="e2eab-150">Create the SPNs:</span></span>  
  
    1.  <span data-ttu-id="e2eab-151">Cree un SPN para el FQDN del equipo de IIS/SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e2eab-151">Create an SPN for the FQDN of the IIS/SharePoint computer:</span></span>  
  
        ```  
        setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
        ```  
  
    2.  <span data-ttu-id="e2eab-152">Cree un SPN para el nombre de NETBIOS del equipo de IIS/SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e2eab-152">Create an SPN for the NETBIOS name of the IIS/SharePoint computer:</span></span>  
  
        ```  
        setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
        ```  
  
    3.  <span data-ttu-id="e2eab-153">Cree un SPN para el FQDN del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e2eab-153">Create an SPN for the FQDN of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
        ```  
  
    4.  <span data-ttu-id="e2eab-154">Cree un SPN para el FQDN y el TCP Port del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e2eab-154">Create an SPN for the FQDN and TCP Port of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
    5.  <span data-ttu-id="e2eab-155">Cree un SPN para el nombre de NETBIOS del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e2eab-155">Create an SPN for the NETBIOS name of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
        ```  
  
    6.  <span data-ttu-id="e2eab-156">Cree un SPN para el nombre de NETBIOS, el puerto TCP del equipo de SQL Server utilizado por el equipo de IIS/SharePoint:</span><span class="sxs-lookup"><span data-stu-id="e2eab-156">Create an SPN for the NETBIOS name:TCP Port of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  
  
        ```  
        setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
        ```  
  
3.  <span data-ttu-id="e2eab-157">En el controlador de dominio, vaya a **usuarios de Active Directory y equipos** y realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2eab-157">On the Domain controller, go to **Active Directory Users & Computers** and do the following:</span></span>  
  
    1.  <span data-ttu-id="e2eab-158">Comprobar **confiar en este equipo para la delegación a cualquier servicio** para los siguientes equipos:</span><span class="sxs-lookup"><span data-stu-id="e2eab-158">Check **Trust this computer for delegation to any service** for the following computers:</span></span>  
  
        -   <span data-ttu-id="e2eab-159">Servidor de SharePoint/IIS</span><span class="sxs-lookup"><span data-stu-id="e2eab-159">SharePoint/IIS server</span></span>  
  
        -   <span data-ttu-id="e2eab-160">SQL Server utilizado por SharePoint</span><span class="sxs-lookup"><span data-stu-id="e2eab-160">SQL Server used by SharePoint</span></span>  
  
    2.  <span data-ttu-id="e2eab-161">Comprobar **cuenta es de confianza para delegación** y desactive la opción **cuenta es importante y no se puede delegar** para las cuentas de dominio siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2eab-161">Check **Account is Trusted for Delegation** and uncheck **Account is sensitive and cannot be delegated** for the following domain accounts:</span></span>  
  
        -   <span data-ttu-id="e2eab-162">Cuenta de dominio de servicio de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e2eab-162">SQL Server service domain account</span></span>  
  
        -   <span data-ttu-id="e2eab-163">Cuenta de dominio del grupo de aplicaciones de IIS</span><span class="sxs-lookup"><span data-stu-id="e2eab-163">IIS Application Pool domain account</span></span>  
  
 <span data-ttu-id="e2eab-164">Para solucionar problemas adicionales, vaya a [solucionar problemas del adaptador de Windows SharePoint Services](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="e2eab-164">For additional troubleshooting, go to [Troubleshooting the Windows SharePoint Services Adapter](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2eab-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2eab-165">See Also</span></span>  
 <span data-ttu-id="e2eab-166">[Configurar SharePoint servicios de ubicación de recepción](../core/configure-sharepoint-services-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="e2eab-166">[Configure SharePoint Services Receive Location](../core/configure-sharepoint-services-receive-location.md) </span></span>  
 <span data-ttu-id="e2eab-167">[Configurar el puerto de envío de SharePoint Services](../core/configure-sharepoint-services-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="e2eab-167">[Configure SharePoint Services Send Port](../core/configure-sharepoint-services-send-port.md) </span></span>  
 [<span data-ttu-id="e2eab-168">CSOM: Adaptador de servicios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e2eab-168">CSOM: SharePoint Services Adapter</span></span>](../core/csom-sharepoint-services-adapter.md)