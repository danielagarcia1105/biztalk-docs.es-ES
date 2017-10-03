---
title: Utilizar el adaptador de base de datos de Oracle con SharePoint | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 254204e5-3b5d-4e70-97ab-817660d1206a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cf5be42a008cadba648739037797160386a42fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a><span data-ttu-id="ca89b-102">Utilizar el adaptador de base de datos de Oracle con SharePoint</span><span class="sxs-lookup"><span data-stu-id="ca89b-102">Use the Oracle Database Adapter with SharePoint</span></span>
<span data-ttu-id="ca89b-103">El Asistente de desarrollo del servicio de adaptador de WCF para [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] habilita el adaptador de Microsoft BizTalk para que base de datos de Oracle y Microsoft BizTalk Adapter para Oracle E-Business Suite a ser consumidos directamente como un origen de datos externo de Microsoft SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ca89b-103">The WCF Adapter Service Development Wizard for [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] enables the Microsoft BizTalk Adapter for Oracle Database and the Microsoft BizTalk Adapter for Oracle E-Business Suite to be directly consumed as an external datasource in Microsoft SharePoint.</span></span> <span data-ttu-id="ca89b-104">El Asistente para agregar un desarrollo de servicio que admita esta característica se inicia con la **servicio de adaptador de WCF** plantilla para crear un nuevo Visual C# sitios Web en [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca89b-104">The Add Service Development Wizard that supports this feature is launched with the **WCF Adapter Service** template for creating a new Visual C# Web Sites in [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="ca89b-105">La plantilla se incluye con la [!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca89b-105">The template is included with the [!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ca89b-106">También debe instalar el SDK de adaptador de línea de negocio (LOB) de Microsoft Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ca89b-106">You must also install the Microsoft Windows Communication Foundation (WCF) Line of Business (LOB) Adapter SDK.</span></span>  
  
## <a name="sharepoint-operation-support"></a><span data-ttu-id="ca89b-107">Compatibilidad de la operación de SharePoint</span><span class="sxs-lookup"><span data-stu-id="ca89b-107">SharePoint Operation Support</span></span>  
 <span data-ttu-id="ca89b-108">El Asistente de desarrollo del servicio de adaptador genera un contrato de servicio especial para los adaptadores de Oracle que es compatible con Microsoft SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ca89b-108">The Adapter Service Development wizard generates a special service contract for the Oracle adapters that is compatible with Microsoft SharePoint.</span></span> <span data-ttu-id="ca89b-109">El asistente generará un contrato de servicio que incluye las siguientes operaciones para integrar el adaptador con Microsoft SharePoint:</span><span class="sxs-lookup"><span data-stu-id="ca89b-109">The wizard will generate a service contract which includes the following operations for integrating the adapter with Microsoft SharePoint:</span></span>  
  
-   <span data-ttu-id="ca89b-110">**Crear:** admitida por la operación de CreateItem_.</span><span class="sxs-lookup"><span data-stu-id="ca89b-110">**Create:** Supported by the CreateItem_ operation.</span></span>  
  
-   <span data-ttu-id="ca89b-111">**Lectura:** admitida por la operación de ReadItem_.</span><span class="sxs-lookup"><span data-stu-id="ca89b-111">**Read:** Supported by the ReadItem_ operation.</span></span>  
  
-   <span data-ttu-id="ca89b-112">**Actualización:** compatible con la operación de UpdateItem_.</span><span class="sxs-lookup"><span data-stu-id="ca89b-112">**Update:** Supported by the UpdateItem_ operation.</span></span>  
  
-   <span data-ttu-id="ca89b-113">**Delete:** admitida por la operación de DeleteItem_.</span><span class="sxs-lookup"><span data-stu-id="ca89b-113">**Delete:** Supported by the DeleteItem_ operation.</span></span>  
  
-   <span data-ttu-id="ca89b-114">**Consulta:** admitida por la operación ReadList.</span><span class="sxs-lookup"><span data-stu-id="ca89b-114">**Query:** Supported by the ReadList operation.</span></span>  
  
-   <span data-ttu-id="ca89b-115">**Asociar:** admitida por la operación de Associate_.</span><span class="sxs-lookup"><span data-stu-id="ca89b-115">**Associate:** Supported by the Associate_ operation.</span></span>  
  
 <span data-ttu-id="ca89b-116">El siguiente contrato de servicio se ha generado mediante el adaptador de Microsoft BizTalk para base de datos de Oracle como un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-116">The following service contract was generated using for the Microsoft BizTalk Adapter for Oracle Database as an example.</span></span> <span data-ttu-id="ca89b-117">El adaptador está configurado para proporcionar acceso a la tabla EMP</span><span class="sxs-lookup"><span data-stu-id="ca89b-117">The adapter is configured to provide access to the EMP table</span></span>  
  
```  
[System.ServiceModel.ServiceContractAttribute()]  
public interface ISCOTT_EMP {  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadList(System.Nullable<int> Limit);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void CreateItem(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void UpdateItem_EMPNO(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void DeleteItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] Associate_DEPTNO(System.Nullable<decimal> DEPTNO);  
}  
```  
  
## <a name="creating-a-new-web-site-to-host-the-microsoft-biztalk-adapter-for-oracle-database-in-iis"></a><span data-ttu-id="ca89b-118">Crear un nuevo sitio Web para hospedar el adaptador de Microsoft BizTalk para la base de datos de Oracle en IIS</span><span class="sxs-lookup"><span data-stu-id="ca89b-118">Creating a New Web Site to Host the Microsoft BizTalk Adapter for Oracle Database in IIS</span></span>  
 <span data-ttu-id="ca89b-119">Estos pasos proporcionan un ejemplo de cómo utilizar al Asistente de desarrollo de servicio del adaptador de WCF, para crear un nuevo servicio web WCF aloja el adaptador de Microsoft BizTalk para base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ca89b-119">These steps provide an example using the WCF Adapter Service Development Wizard, to create a new WCF web service hosting the Microsoft BizTalk Adapter for Oracle Database.</span></span> <span data-ttu-id="ca89b-120">El contrato de servicios incluye operaciones directamente compatibles con Sharepoint.</span><span class="sxs-lookup"><span data-stu-id="ca89b-120">The service contract will include operations directly compatible with Sharepoint.</span></span> <span data-ttu-id="ca89b-121">Por lo que se puede consumir directamente como un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-121">So that it can be directly consumed as an external datasource.</span></span> <span data-ttu-id="ca89b-122">El adaptador se configura para autenticar con la base de datos de Oracle mediante la **SCOTT** cuenta.</span><span class="sxs-lookup"><span data-stu-id="ca89b-122">The adapter is configured to authenticate with the Oracle database using the **SCOTT** account.</span></span> <span data-ttu-id="ca89b-123">Si el **SCOTT** cuenta está bloqueada, no se puede desbloquear la cuenta iniciando sesión en SQL Plus como SYSDBA.</span><span class="sxs-lookup"><span data-stu-id="ca89b-123">If the **SCOTT** account is locked, you can unlock the account by logging into SQL Plus as SYSDBA.</span></span>  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 <span data-ttu-id="ca89b-124">A continuación, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ca89b-124">Then run the following command.</span></span>  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="creating-the-new-web-site-project"></a><span data-ttu-id="ca89b-125">Crear el nuevo proyecto de sitio Web</span><span class="sxs-lookup"><span data-stu-id="ca89b-125">Creating the New Web Site Project</span></span>  
  
1.  <span data-ttu-id="ca89b-126">Iniciar **Microsoft [!INCLUDE[vs2012](../../includes/vs2012-md.md)]** .</span><span class="sxs-lookup"><span data-stu-id="ca89b-126">Start **Microsoft [!INCLUDE[vs2012](../../includes/vs2012-md.md)]**.</span></span>  
  
2.  <span data-ttu-id="ca89b-127">En [!INCLUDE[vs2010](../../includes/vs2010-md.md)], en la **archivo** menú, seleccione **New** y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-127">In [!INCLUDE[vs2010](../../includes/vs2010-md.md)], on the **File** menu, select **New** and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="ca89b-128">En el **nuevo proyecto** cuadro de diálogo, expanda **otros lenguajes** y haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-128">In the **New Project** dialog box, expand **Other Languages** and click **Visual C#**.</span></span> <span data-ttu-id="ca89b-129">Buscar el **servicio de adaptador de WCF** en la plantilla de lista y haga clic en ella para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="ca89b-129">Find the **WCF Adapter Service** in the template list and click it to select it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca89b-130">El **servicio de adaptador de WCF** plantilla no está disponible si la [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)] no está instalado.</span><span class="sxs-lookup"><span data-stu-id="ca89b-130">The **WCF Adapter Service** template is not available if the [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)] is not installed.</span></span> <span data-ttu-id="ca89b-131">En x64 de sistemas, se instalan las versiones x86 y x64 de la [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca89b-131">On x64 systems, install both the x86 and x64 versions of the [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)].</span></span>  
  
4.  <span data-ttu-id="ca89b-132">Especifique **ScottEMP** para el nombre y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-132">Specify **ScottEMP** for the name, and then click **OK**.</span></span> <span data-ttu-id="ca89b-133">El **Asistente para desarrollo de servicio de adaptador de WCF** inicia.</span><span class="sxs-lookup"><span data-stu-id="ca89b-133">The **WCF Adapter Service Development Wizard** starts.</span></span>  
  
5.  <span data-ttu-id="ca89b-134">En el **Introducción** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-134">On the **Introduction** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="ca89b-135">En el **elegir operaciones** página, especifique la **oracleDBBinding** enlace.</span><span class="sxs-lookup"><span data-stu-id="ca89b-135">On the **Choose Operations** page, specify the **oracleDBBinding** binding.</span></span>  
  
7.  <span data-ttu-id="ca89b-136">Haga clic en el **configurar** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-136">Click the **Configure** button.</span></span> <span data-ttu-id="ca89b-137">El **configurar el adaptador** se muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-137">The **Configure Adapter** dialog is displayed.</span></span>  
  
8.  <span data-ttu-id="ca89b-138">En el **seguridad** ficha, seleccione **nombre de usuario** en el **tipo de credencial de cliente** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ca89b-138">On the **Security** tab, select **Username** in the **Client credential type** dropdown list box.</span></span>  
  
9. <span data-ttu-id="ca89b-139">Escriba **SCOTT** para el usuario el nombre y escriba la contraseña correcta para la cuenta de SCOTT.</span><span class="sxs-lookup"><span data-stu-id="ca89b-139">Enter **SCOTT** for the User name and enter the correct password for the SCOTT account.</span></span> <span data-ttu-id="ca89b-140">Es la contraseña predeterminada para la cuenta de SCOTT **"Tiger"**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-140">The default password for the SCOTT account is **tiger**.</span></span>  
  
10. <span data-ttu-id="ca89b-141">Haga clic en el **propiedades de URI** ficha, escriba el nombre de host o dirección IP para el servidor de Oracle en el **ServerAddress** cuadro.</span><span class="sxs-lookup"><span data-stu-id="ca89b-141">Click the **URI Properties** tab, enter the IP address or host name for your Oracle server in the **ServerAddress** box.</span></span>  
  
11. <span data-ttu-id="ca89b-142">Escriba el nombre de instancia correcto de servicio base de datos de Oracle en el **ServiceName** cuadro.</span><span class="sxs-lookup"><span data-stu-id="ca89b-142">Enter the correct Oracle database service instance name in the **ServiceName** box.</span></span> <span data-ttu-id="ca89b-143">Puede copiar la información de nombre de instancia de Oracle Enterprise Manager.</span><span class="sxs-lookup"><span data-stu-id="ca89b-143">You can copy the instance name information from Oracle Enterprise Manager.</span></span>  
  
12. <span data-ttu-id="ca89b-144">Presione el **Aceptar** situado en la **configurar el adaptador** cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="ca89b-144">Press the **OK** button on the **Configure Adapter** dialog</span></span>  
  
13. <span data-ttu-id="ca89b-145">En el **elegir operaciones** página del asistente, haga clic en el **conectar** botón y espere unos minutos para las categorías que se van a compilar en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ca89b-145">On the **Choose Operations** page of the wizard, click the **Connect** button and wait a few moments for the categories to be built for the Oracle database.</span></span>  
  
14. <span data-ttu-id="ca89b-146">Una vez que se agregan las categorías en el **seleccione una categoría de** lista, desplácese hacia abajo hasta **SCOTT** y expándalo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-146">Once the categories are added in the **Select a category** list, scroll down to **SCOTT** and expand it.</span></span> <span data-ttu-id="ca89b-147">A continuación, expanda **tabla** y haga clic en el **EMP** entrada de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ca89b-147">Then expand **Table** and click the **EMP** table entry.</span></span>  
  
15. <span data-ttu-id="ca89b-148">En el **categorías y operaciones disponibles** lista, seleccione todas las operaciones en la lista y haga clic en el **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-148">In the **Available categories and operations** list, select all the operations in the list and click the **Add** button.</span></span> <span data-ttu-id="ca89b-149">Todas las operaciones se agregan a la **agregar categorías y operaciones** lista.</span><span class="sxs-lookup"><span data-stu-id="ca89b-149">All the operations are added to the **Added categories and operations** list.</span></span>  
  
16. <span data-ttu-id="ca89b-150">En el **elegir operaciones** página, haga clic en el **siguiente** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-150">On the **Choose Operations** page, click the **Next** button.</span></span>  
  
17. <span data-ttu-id="ca89b-151">En el **configurar el servicio y los comportamientos de extremo** , establezca el **UseServiceCertificate** el comportamiento de servicio **false** para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-151">On the **Configure Service and Endpoint Behaviors** page, set the **UseServiceCertificate** Service behavior to **false** for this example.</span></span> <span data-ttu-id="ca89b-152">A continuación, haga clic en el **siguiente** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-152">Then click the **Next** button.</span></span>  
  
18. <span data-ttu-id="ca89b-153">En el **configurar el enlace de punto de conexión de servicio y dirección** página, haga clic en el **aplicar** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-153">On the **Configure Service Endpoint Binding and Address** page, click the **Apply** button.</span></span> <span data-ttu-id="ca89b-154">A continuación, haga clic en el **siguiente** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-154">Then click the **Next** button.</span></span>  
  
19. <span data-ttu-id="ca89b-155">En el **resumen** página, haga clic en el **finalizar** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-155">On the **Summary** page, click the **Finish** button.</span></span>  
  
20. <span data-ttu-id="ca89b-156">Haga clic en el **generar** opción de menú y, a continuación, haga clic en **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-156">Click the **Build** menu option and then click **Build Solution**.</span></span> <span data-ttu-id="ca89b-157">Comprobar que la compilación del proyecto se realizó correctamente sin errores.</span><span class="sxs-lookup"><span data-stu-id="ca89b-157">Verify the project build was successful with no errors.</span></span>  
  
## <a name="publishing-the-new-service-to-iis"></a><span data-ttu-id="ca89b-158">Publica el nuevo servicio en IIS</span><span class="sxs-lookup"><span data-stu-id="ca89b-158">Publishing the New Service to IIS</span></span>  
 <span data-ttu-id="ca89b-159">En este ejemplo publicará el servicio de adaptador de host en el servidor web IIS local.</span><span class="sxs-lookup"><span data-stu-id="ca89b-159">For this example you will publish the adapter host service to the local IIS web server.</span></span>  
  
1.  <span data-ttu-id="ca89b-160">En el Explorador de soluciones para [!INCLUDE[vs2010](../../includes/vs2010-md.md)], haga clic con el **ScottEmp** del proyecto y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-160">In Solution Explorer for [!INCLUDE[vs2010](../../includes/vs2010-md.md)], right click the **ScottEmp** project and click **Properties**.</span></span> <span data-ttu-id="ca89b-161">Se muestran las fichas del Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="ca89b-161">The Project Designer tabs are displayed.</span></span>  
  
2.  <span data-ttu-id="ca89b-162">Haga clic en el **Web** ficha, a continuación, haga clic en el **servidor Web de IIS Local utilice** opción.</span><span class="sxs-lookup"><span data-stu-id="ca89b-162">Click the **Web** tab, then click the **Use Local IIS Web server** option.</span></span>  
  
3.  <span data-ttu-id="ca89b-163">Haga clic en el **crear directorio Virtual** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-163">Click the **Create Virtual Directory** button.</span></span>  
  
4.  <span data-ttu-id="ca89b-164">Abra un explorador web a la dirección de servicio **http://localhost/ScottEmp/ISCOTT_EMP.svc**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-164">Open a web browser to the service address **http://localhost/ScottEmp/ISCOTT_EMP.svc**.</span></span> <span data-ttu-id="ca89b-165">Debería recibir un mensaje que indica "Se ha creado un servicio" que indica el adaptador está alojado en IIS.</span><span class="sxs-lookup"><span data-stu-id="ca89b-165">You should receive a message stating “You have created a service” indicating the adapter is hosted in IIS.</span></span>  
  
## <a name="adding-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a><span data-ttu-id="ca89b-166">Agregar el origen de datos externo en un sitio de SharePoint con SharePoint Designer</span><span class="sxs-lookup"><span data-stu-id="ca89b-166">Adding the External Data Source to a SharePoint Site using SharePoint Designer</span></span>  
 <span data-ttu-id="ca89b-167">En esta sección se describe cómo agregar el servicio de WCF como origen de datos externo a un nuevo sitio Web con SharePoint Designer.</span><span class="sxs-lookup"><span data-stu-id="ca89b-167">This section describes how to add the WCF Service as an external data source to a new Web Site using SharePoint Designer.</span></span>  
  
#### <a name="adding-the-external-data-source"></a><span data-ttu-id="ca89b-168">Agregar el origen de datos externos</span><span class="sxs-lookup"><span data-stu-id="ca89b-168">Adding the External Data source</span></span>  
  
1.  <span data-ttu-id="ca89b-169">Abra SharePoint Designer y cree un nuevo sitio Web.</span><span class="sxs-lookup"><span data-stu-id="ca89b-169">Open SharePoint Designer and create a new Web Site.</span></span>  
  
2.  <span data-ttu-id="ca89b-170">En SharePoint Designer, expanda **navegación** y haga clic en **tipos de contenido externo** en el **objetos del sitio** lista.</span><span class="sxs-lookup"><span data-stu-id="ca89b-170">In SharePoint Designer, expand **Navigation** and click **External Content types** in the **Site Objects** list.</span></span>  
  
3.  <span data-ttu-id="ca89b-171">Haga clic en el **tipo de contenido externo** botón de menú para crear un nuevo tipo de contenido externo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-171">Click the **External Content Type** menu button to create a new external content type.</span></span>  
  
4.  <span data-ttu-id="ca89b-172">Haga clic en el texto al lado de **nombre** para modificar el nombre del nuevo tipo de contenido externo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-172">Click the text beside **Name** to edit the name of the new external content type.</span></span> <span data-ttu-id="ca89b-173">Escriba **OracleEMP** para el nombre.</span><span class="sxs-lookup"><span data-stu-id="ca89b-173">Enter **OracleEMP** for the name.</span></span>  
  
5.  <span data-ttu-id="ca89b-174">Haga clic en el vínculo de texto junto a **sistema externo** que dice **haga clic aquí para conocer las operaciones y los orígenes de datos externos.**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-174">Click the text link beside **External System** which says **Click here to discover external data sources and operations.**.</span></span> <span data-ttu-id="ca89b-175">Se abre el Diseñador de operación para el tipo de contenido externo de OracleEMP.</span><span class="sxs-lookup"><span data-stu-id="ca89b-175">This opens the Operation Designer for the OracleEMP external content type.</span></span>  
  
6.  <span data-ttu-id="ca89b-176">Haga clic en el **Agregar conexión** botón en la pantalla de detección.</span><span class="sxs-lookup"><span data-stu-id="ca89b-176">Click the **Add Connection** button on the discovery screen.</span></span>  
  
7.  <span data-ttu-id="ca89b-177">En el cuadro de diálogo de selección de tipo de origen de datos externo, elija **servicio WCF** y haga clic en el **Aceptar** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-177">In the External Data Source Type Selection dialog, choose **WCF Service** and click the **OK** button.</span></span>  
  
8.  <span data-ttu-id="ca89b-178">En el cuadro de diálogo de conexión de WCF, en la **dirección URL de metadatos de servicio** escriba **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**</span><span class="sxs-lookup"><span data-stu-id="ca89b-178">In the WCF Connection dialog, in the **Service Metadata URL** box enter **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**</span></span>  
  
9. <span data-ttu-id="ca89b-179">En el **dirección URL del extremo de servicio** escriba **https://localhost/ScottEmp/ISCOTT_EMP.svc**</span><span class="sxs-lookup"><span data-stu-id="ca89b-179">In the **Service Endpoint URL** box enter **https://localhost/ScottEmp/ISCOTT_EMP.svc**</span></span>  
  
10. <span data-ttu-id="ca89b-180">Haga clic en el **Aceptar** botón para cerrar el cuadro de diálogo de conexión de WCF.</span><span class="sxs-lookup"><span data-stu-id="ca89b-180">Click the **OK** button to close the WCF Connection dialog.</span></span>  
  
11. <span data-ttu-id="ca89b-181">Una vez que se rellene la información de origen de datos, expanda la **https://localhost/ScottEmp/ISCOTT_EMP.svc** origen de datos y expanda **métodos Web**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-181">Once the Data Source information is populated, expand the **https://localhost/ScottEmp/ISCOTT_EMP.svc** data source and expand **Web Methods**.</span></span>  
  
12. <span data-ttu-id="ca89b-182">Haga clic con el **ReadList** método Web y haga clic en **nueva operación de lista de lectura**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-182">Right click the **ReadList** Web Method and click **New Read List Operation**.</span></span> <span data-ttu-id="ca89b-183">Se inicia el cuadro de diálogo de configuración de lista de lectura.</span><span class="sxs-lookup"><span data-stu-id="ca89b-183">The Read List configuration dialog is launched.</span></span>  
  
13. <span data-ttu-id="ca89b-184">En el cuadro de diálogo lista de lectura, haga clic en **devolver parámetros** y haga clic en **EMPNO** en los elementos de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ca89b-184">In the Read List dialog click **Return Parameters** and click **EMPNO** in the Data Source Elements.</span></span> <span data-ttu-id="ca89b-185">Haga clic en el **se asignan a identificador**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-185">Click the **Map to identifier**.</span></span>  
  
14. <span data-ttu-id="ca89b-186">Haga clic en **finalizar** en el cuadro de diálogo lista de lectura.</span><span class="sxs-lookup"><span data-stu-id="ca89b-186">Click **Finish** in the Read List dialog.</span></span>  
  
15. <span data-ttu-id="ca89b-187">Guarde el nuevo origen de datos externo escribiendo **Ctrl + s**.</span><span class="sxs-lookup"><span data-stu-id="ca89b-187">Save the new external data source by typing **Ctrl+s**.</span></span>  
  
#### <a name="testing-the-external-data-source-connection"></a><span data-ttu-id="ca89b-188">Probar la conexión de origen de datos externos</span><span class="sxs-lookup"><span data-stu-id="ca89b-188">Testing the External Data Source Connection</span></span>  
  
1.  <span data-ttu-id="ca89b-189">En el nuevo sitio web, haga clic en el **crear listas y formularios** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-189">In the new web site, click the **Create Lists and Forms** button.</span></span> <span data-ttu-id="ca89b-190">Aparece la lista crear y el formulario de cuadro de diálogo OracleEMP.</span><span class="sxs-lookup"><span data-stu-id="ca89b-190">The Create List and Form for OracleEMP dialog appears.</span></span>  
  
2.  <span data-ttu-id="ca89b-191">Escriba **OracleEMP_List** para el nombre de la lista y haga clic en el **Aceptar** botón.</span><span class="sxs-lookup"><span data-stu-id="ca89b-191">Enter **OracleEMP_List** for the List Name and click the **OK** button.</span></span>  
  
3.  <span data-ttu-id="ca89b-192">Una vez que se crea la lista, haga clic en el **vista resumen** botón en el menú.</span><span class="sxs-lookup"><span data-stu-id="ca89b-192">Once the list is create, click the **Summary View** button on the menu.</span></span>  
  
4.  <span data-ttu-id="ca89b-193">Haga clic en **OracleEMP_List** en listas externas.</span><span class="sxs-lookup"><span data-stu-id="ca89b-193">Click **OracleEMP_List** under External Lists.</span></span>  
  
5.  <span data-ttu-id="ca89b-194">Haga clic en el **vista previa en el explorador** botón en el menú para probar la operación ReadList del adaptador.</span><span class="sxs-lookup"><span data-stu-id="ca89b-194">Click the **Preview in Browser** button on the menu to test the ReadList operation of the adapter.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ca89b-195">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="ca89b-195">Troubleshooting</span></span>  
  
-   <span data-ttu-id="ca89b-196">En equipos de 64 bits debe asegurarse de que también se instalan los componentes de cliente de Oracle de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="ca89b-196">On 64-bit machines you must make sure that 32-bit Oracle client components are also installed.</span></span> <span data-ttu-id="ca89b-197">Esto es porque [!INCLUDE[vs2010](../../includes/vs2010-md.md)] y asistentes del que se ejecutará como un proceso de 32 bits que requieren acceso a componentes de 32 bits durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="ca89b-197">This is because [!INCLUDE[vs2010](../../includes/vs2010-md.md)] and it’s wizards will be running as a 32-bit process requiring access to 32-bit components during development.</span></span>