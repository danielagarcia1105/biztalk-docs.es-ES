---
title: Instalar RFC personalizadas para el proveedor de datos para SAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation, custom RFCs for the Data Provider for SAP
- installing, custom RFCs for the Data Provider for SAP
- installing custom RFCs, how to
ms.assetid: 7a99db70-fa5a-4c04-9dc7-b71613d4364e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aff501e5bf59d6ae22d9ad2a00e0e5ff5ad4605
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a><span data-ttu-id="3a880-102">Instalar RFC personalizadas para el proveedor de datos para SAP</span><span class="sxs-lookup"><span data-stu-id="3a880-102">Install Custom RFCs for the Data Provider for SAP</span></span>
<span data-ttu-id="3a880-103">Instale las RFC personalizadas si desea usar el proveedor de datos de .NET Framework para mySAP Business Suite para tener acceso al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3a880-103">Install the custom RFCs if you want to use the .NET Framework Data Provider for mySAP Business Suite to access the SAP system.</span></span>

<span data-ttu-id="3a880-104">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere RFC personalizadas realizar algunas operaciones en el sistema SAP para:</span><span class="sxs-lookup"><span data-stu-id="3a880-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires custom RFCs to perform some operations on the SAP system to:</span></span>
  
-   <span data-ttu-id="3a880-105">Ejecutar la operación de selección, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere Z_EXTRACT_DATA_OO RFC.</span><span class="sxs-lookup"><span data-stu-id="3a880-105">Run the SELECT operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXTRACT_DATA_OO RFC.</span></span>  
  
-   <span data-ttu-id="3a880-106">Ejecutar la operación de EXECQUERY el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere Z_EXECUTE_SAP_QUERY RFC.</span><span class="sxs-lookup"><span data-stu-id="3a880-106">Run the EXECQUERY operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
<span data-ttu-id="3a880-107">Para llevar a cabo estas operaciones en el sistema SAP, debe instalar estos RFC personalizadas en el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="3a880-107">To perform these operations on the SAP system, you must install these custom RFCs on the SAP system.</span></span> <span data-ttu-id="3a880-108">Si decide instalar la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] junto con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], el programa de instalación copia el transporte RFC para el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] como un archivo comprimido (customRFC.zip) en el sistema donde se instala el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3a880-108">If you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] along with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the Setup program copies the RFC transport for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as a compressed file (customRFC.zip) on the system where you install the adapter.</span></span> <span data-ttu-id="3a880-109">El archivo zip se instala normalmente en  *\<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider para mySAP Business Suite*.</span><span class="sxs-lookup"><span data-stu-id="3a880-109">The zip file is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider for mySAP Business Suite*.</span></span> 
  
 <span data-ttu-id="3a880-110">Después de extraer el archivo zip, encontrará cuatro archivos de datos, dos siguiendo la denominación de patrón K9 *. BI1 (por ejemplo, similar a K900534. BI1) y los otros dos sigue el patrón R9\*. BI1 (por ejemplo, similar a R900534. BI1).</span><span class="sxs-lookup"><span data-stu-id="3a880-110">After extracting the zip file, you will find four data files, two following the naming pattern K9*.BI1 (for example, similar to K900534.BI1), and the other two following the pattern R9\*.BI1 (for example, similar to R900534.BI1).</span></span>  
  

  
1.  <span data-ttu-id="3a880-111">Copie los archivos extraídos del equipo que ejecuta los adaptadores para el servidor de aplicaciones de SAP.</span><span class="sxs-lookup"><span data-stu-id="3a880-111">Copy the extracted files from the computer running the adapters to the SAP application server.</span></span>  
  
    1.  <span data-ttu-id="3a880-112">Inicie sesión como el administrador del sistema SAP R/3 al servidor de aplicaciones de SAP de su sistema de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3a880-112">Log in as the SAP R/3 system administrator to the SAP application server of your development system.</span></span>  
  
    2.  <span data-ttu-id="3a880-113">Copie los archivos de dos transporte con el patrón de nomenclatura K9 *. BI1 desde el directorio de instalación en el equipo que ejecuta los adaptadores en el siguiente directorio en el servidor de aplicaciones de SAP:</span><span class="sxs-lookup"><span data-stu-id="3a880-113">Copy the two transport files with the naming pattern K9*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
         `<drive>:\usr\sap\trans\cofiles`  
  
    3.  <span data-ttu-id="3a880-114">Copie los archivos de dos transporte con el patrón de nomenclatura R9 *. BI1 desde el directorio de instalación en el equipo que ejecuta los adaptadores en el siguiente directorio en el servidor de aplicaciones de SAP:</span><span class="sxs-lookup"><span data-stu-id="3a880-114">Copy the two transport files with the naming pattern R9*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
         `<drive>:\usr\sap\trans\data`  
  
2.  <span data-ttu-id="3a880-115">Cargar el transporte en el búfer de transporte en el servidor de aplicaciones de SAP.</span><span class="sxs-lookup"><span data-stu-id="3a880-115">Load the transport into the transport buffer on the SAP application server.</span></span>  
  
    1.  <span data-ttu-id="3a880-116">En el símbolo del sistema, desplácese al directorio del programa de transporte en el servidor de aplicaciones de SAP:</span><span class="sxs-lookup"><span data-stu-id="3a880-116">At the command prompt, navigate to the transport program directory on the SAP application server:</span></span>  
  
         `<drive>:\usr\sap\trans\bin`  
  
    2.  <span data-ttu-id="3a880-117">Para cargar el transporte en el búfer de transporte, ejecute el comando siguiente en el `\usr\sap\trans\bin` directorio y reemplazar *sysid* con el identificador de sistema de su sistema de desarrollo:</span><span class="sxs-lookup"><span data-stu-id="3a880-117">To load the transport into the transport buffer, execute the following command at the `\usr\sap\trans\bin` directory and replace *sysid* with the system ID of your development system:</span></span>  
  
        ```  
        tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         <span data-ttu-id="3a880-118">WHERE, *TransportNumber* es el número real de transporte (por ejemplo BI1K900534).</span><span class="sxs-lookup"><span data-stu-id="3a880-118">where, *TransportNumber* is the actual transport number (for example BI1K900534).</span></span>  
  
    3.  <span data-ttu-id="3a880-119">Después de la `tp` comando finalice, verá un informe similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a880-119">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        Addtobuffer successful for TransportNumber  
        tp finished with return code: 0  
        ```  
  
         <span data-ttu-id="3a880-120">Código de retorno "0" significa que la operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a880-120">Return code "0" means that the operation succeeded.</span></span>  
  
         <span data-ttu-id="3a880-121">Un código de retorno de 0 ó 4 es aceptable.</span><span class="sxs-lookup"><span data-stu-id="3a880-121">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="3a880-122">Póngase en contacto con Microsoft servicio y soporte técnico, si recibe un código de retorno de 8 o superior.</span><span class="sxs-lookup"><span data-stu-id="3a880-122">Contact Microsoft Customer Service and Support, if you receive a return code of 8 or above.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="3a880-123">Repita los pasos (b) y (c) para el segundo conjunto de archivos de transporte.</span><span class="sxs-lookup"><span data-stu-id="3a880-123">Repeat steps (b) and (c) for the second set of transport files.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3a880-124">Puede deducir con facilidad el número real de transporte del nombre de archivo cofile.</span><span class="sxs-lookup"><span data-stu-id="3a880-124">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="3a880-125">Por ejemplo, un cofile denominado K900534. BI1 proporciona una serie de transporte de BI1K900534.</span><span class="sxs-lookup"><span data-stu-id="3a880-125">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
3.  <span data-ttu-id="3a880-126">Importar el transporte de SAP.</span><span class="sxs-lookup"><span data-stu-id="3a880-126">Import the transport into SAP.</span></span>  
  
    1.  <span data-ttu-id="3a880-127">Ejecute el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="3a880-127">Execute the following command at the command prompt:</span></span>  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         <span data-ttu-id="3a880-128">Reemplace *sysid* con el identificador de sistema de su sistema de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3a880-128">Replace *sysid* with the system ID of your development system.</span></span> <span data-ttu-id="3a880-129">Reemplace *clientnumber* con el número de cliente de su sistema de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3a880-129">Replace *clientnumber* with the client number of your development system.</span></span>  
  
         <span data-ttu-id="3a880-130">Puede utilizar el parámetro U2 para sobrescribir objetos instalados previamente, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3a880-130">You can use the U2 parameter to overwrite previously installed objects, as follows:</span></span>  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> U2  
        ```  
  
         <span data-ttu-id="3a880-131">o bien</span><span class="sxs-lookup"><span data-stu-id="3a880-131">or</span></span>  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="3a880-132">Puede deducir con facilidad el número real de transporte del nombre de archivo cofile.</span><span class="sxs-lookup"><span data-stu-id="3a880-132">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="3a880-133">Por ejemplo, un cofile denominado K900534. BI1 proporciona una serie de transporte de BI1K900534.</span><span class="sxs-lookup"><span data-stu-id="3a880-133">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
    2.  <span data-ttu-id="3a880-134">Después de la `tp` comando finalice, verá un informe similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a880-134">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        tp finished with return code: 0  
        ```  
  
         <span data-ttu-id="3a880-135">Código de retorno "0" significa que la operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a880-135">Return code "0" means that the operation succeeded.</span></span>  
  
         <span data-ttu-id="3a880-136">Un código de retorno de 0 ó 4 es aceptable.</span><span class="sxs-lookup"><span data-stu-id="3a880-136">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="3a880-137">Si recibe un código de retorno de 8 o superior, póngase en contacto con soporte técnico y el servicio de cliente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3a880-137">Contact Microsoft Customer Service and Support if you receive a return code of 8 or above.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="3a880-138">Repita los pasos (a) y (b) para el segundo conjunto de archivos de transporte.</span><span class="sxs-lookup"><span data-stu-id="3a880-138">Repeat steps (a) and (b) for the second set of transport files.</span></span>  
  
4.  <span data-ttu-id="3a880-139">Compruebe el registro de transporte.</span><span class="sxs-lookup"><span data-stu-id="3a880-139">Check the transport log.</span></span>  
  
5.  <span data-ttu-id="3a880-140">Compruebe el registro de transporte en el organizador de transporte de GUI de SAP mediante transacciones SE09 para comprobar que no hay ningún error.</span><span class="sxs-lookup"><span data-stu-id="3a880-140">Check the transport log in SAP GUI Transport Organizer using transaction SE09 to verify that there are no errors.</span></span>  
  
 <span data-ttu-id="3a880-141">Configuración de autorización del usuario</span><span class="sxs-lookup"><span data-stu-id="3a880-141">Setting User Authorization</span></span>  
 <span data-ttu-id="3a880-142">La solicitud de cambio de Z_EXTRACT_DATA_OO requiere el Id. de usuario con objetos de autorización específica.</span><span class="sxs-lookup"><span data-stu-id="3a880-142">The Z_EXTRACT_DATA_OO RFC requires user IDs with specific authorization objects.</span></span> <span data-ttu-id="3a880-143">Use las herramientas de administración de la autorización de GUI de SAP para establecer las restricciones mínimas en la ejecución de la solicitud de cambio:</span><span class="sxs-lookup"><span data-stu-id="3a880-143">Use the SAP GUI authorization administration tools to set the minimum restrictions on the execution of the RFC:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a880-144">No es necesario establecer la autorización para la solicitud de cambio de Z_EXECUTE_SAP_QUERY.</span><span class="sxs-lookup"><span data-stu-id="3a880-144">You do not need to set the authorization for the Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
-   <span data-ttu-id="3a880-145">Z_EXTRACT_DATA_OO requiere S_TABU_DIS y Z_EIP_TABL.</span><span class="sxs-lookup"><span data-stu-id="3a880-145">Z_EXTRACT_DATA_OO requires both S_TABU_DIS and Z_EIP_TABL.</span></span> <span data-ttu-id="3a880-146">Los valores siguientes proporcionan las restricciones de mínimas de S_TABU_DIS, lo que permite a los usuarios ver metadatos de las tablas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3a880-146">The following values provide the minimum restrictions for S_TABU_DIS, which allow users to view metadata for any table in the system.</span></span>  
  
    -   <span data-ttu-id="3a880-147">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="3a880-147">ACTVT: 03</span></span>  
  
    -   <span data-ttu-id="3a880-148">DICBERCLS: *</span><span class="sxs-lookup"><span data-stu-id="3a880-148">DICBERCLS: *</span></span>  
  
     <span data-ttu-id="3a880-149">Puede usar DICBERCLS para restringir autorización a las tablas mediante la clase de autorización.</span><span class="sxs-lookup"><span data-stu-id="3a880-149">You can use DICBERCLS to restrict authorization to tables by authorization class.</span></span>  
  
     <span data-ttu-id="3a880-150">Puede usar la tabla TDDAT para ver la clase de autorización para las tablas.</span><span class="sxs-lookup"><span data-stu-id="3a880-150">You can use the TDDAT table to view the authorization class for tables.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3a880-151">Para evitar cambios en las tablas por las transacciones de mantenimiento de tabla, solo debe conceder privilegios de visualización en un entorno de producción (ACTVT: 03 establece la actividad permitida para mostrar).</span><span class="sxs-lookup"><span data-stu-id="3a880-151">To prevent changes to tables by table maintenance transactions, you should only grant display privileges in a production environment (ACTVT: 03 sets the permissible activity to display).</span></span>  
  
     <span data-ttu-id="3a880-152">Los valores mínimos de Z_EIP_TABL son:</span><span class="sxs-lookup"><span data-stu-id="3a880-152">The minimum values for Z_EIP_TABL are:</span></span>  
  
    -   <span data-ttu-id="3a880-153">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="3a880-153">ACTVT: 03</span></span>  
  
    -   <span data-ttu-id="3a880-154">TABLA: *</span><span class="sxs-lookup"><span data-stu-id="3a880-154">TABLE: *</span></span>  
  
     <span data-ttu-id="3a880-155">Puede usar la tabla para definir explícitamente las tablas autorizadas.</span><span class="sxs-lookup"><span data-stu-id="3a880-155">You can use TABLE to explicitly define the authorized tables.</span></span> <span data-ttu-id="3a880-156">Observe también que S_TABU_DIS también se utiliza en otras transacciones.</span><span class="sxs-lookup"><span data-stu-id="3a880-156">Note, too, that S_TABU_DIS is also used in other transactions.</span></span>  
  
##### <a name="to-set-user-authorization"></a><span data-ttu-id="3a880-157">Para establecer la autorización del usuario</span><span class="sxs-lookup"><span data-stu-id="3a880-157">To set user authorization</span></span>  
  
1.  <span data-ttu-id="3a880-158">Inicie la GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="3a880-158">Start the SAP GUI.</span></span> <span data-ttu-id="3a880-159">Vaya al código de T, tipo `pfcg`, y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3a880-159">Go to T-code, type `pfcg`, and press ENTER.</span></span>  
  
2.  <span data-ttu-id="3a880-160">En el **rol** texto cuadro, escriba un nombre de rol que desea crear, por ejemplo, `ZTEST`y, a continuación, haga clic en **rol**.</span><span class="sxs-lookup"><span data-stu-id="3a880-160">In the **Role** text box, enter a role name you want to create, for example, `ZTEST`, and then click **Role**.</span></span>  
  
3.  <span data-ttu-id="3a880-161">En el **Create Role** página, haga clic en el **autorizaciones** ficha.</span><span class="sxs-lookup"><span data-stu-id="3a880-161">In the **Create Role** page, click the **Authorizations** tab.</span></span>  
  
     <span data-ttu-id="3a880-162">Si se le pide al guardar el rol, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3a880-162">If prompted to save the role, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="3a880-163">En el **cambiar funciones** página, haga clic en el **datos de autorización de cambio** botón.</span><span class="sxs-lookup"><span data-stu-id="3a880-163">In the **Change Roles** page, click the **Change Authorization Data** button.</span></span>  
  
5.  <span data-ttu-id="3a880-164">Si se le pedirá que seleccione una plantilla en el **Elegir plantilla** cuadro de diálogo, haga clic en **no seleccione plantillas**.</span><span class="sxs-lookup"><span data-stu-id="3a880-164">If you are prompted to select a template from the **Choose Template** dialog box, click **Do not select templates**.</span></span>  
  
6.  <span data-ttu-id="3a880-165">En el **cambio de rol: autorizaciones** página, haga clic en el **manualmente** botón.</span><span class="sxs-lookup"><span data-stu-id="3a880-165">In the **Change role: Authorizations** page, click the **Manually** button.</span></span>  
  
7.  <span data-ttu-id="3a880-166">En el **selección Manual de autorizaciones** cuadro, escriba el nombre del objeto de autorización `Z_EIP_TABL` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="3a880-166">In the **Manual selection of authorizations** box, enter the name of the authorization object `Z_EIP_TABL` and press ENTER.</span></span>  
  
8.  <span data-ttu-id="3a880-167">En el **cambio de rol: autorizaciones** página, expanda los nodos hasta que vea los cuadros de texto para **actividad** y **nombre de la tabla**.</span><span class="sxs-lookup"><span data-stu-id="3a880-167">In the **Change role: Authorizations** page, expand the nodes until you see the text boxes for **Activity** and **Table Name**.</span></span> <span data-ttu-id="3a880-168">Para el **actividad** texto cuadro, escriba el valor `03`.</span><span class="sxs-lookup"><span data-stu-id="3a880-168">For the **Activity** text box, enter the value `03`.</span></span> <span data-ttu-id="3a880-169">Para el **nombre de la tabla** texto cuadro, escriba el valor `*`.</span><span class="sxs-lookup"><span data-stu-id="3a880-169">For the **Table Name** text box, enter the value `*`.</span></span>  
  
9. <span data-ttu-id="3a880-170">Haga clic en el **guardar** botón para generar el perfil.</span><span class="sxs-lookup"><span data-stu-id="3a880-170">Click the **Save** button to generate the profile.</span></span>  
  
10. <span data-ttu-id="3a880-171">Vuelva a la **cambiar funciones** página y haga clic en el **usuario** ficha.</span><span class="sxs-lookup"><span data-stu-id="3a880-171">Go back to the **Change Roles** page and click the **User** tab.</span></span>  
  
11. <span data-ttu-id="3a880-172">En el **usuario** ficha, asigne un Id. de usuario para el rol escribiendo el nombre de usuario en el **Id. de usuario** columna y haga clic en el **comparación usuario** botón.</span><span class="sxs-lookup"><span data-stu-id="3a880-172">In the **User** tab, assign a user ID for the role by entering the user name in the **User ID** column, and click the **User comparison** button.</span></span>  
  
12. <span data-ttu-id="3a880-173">En el **comparar el registro de rol de usuario maestro**, haga clic en **completar comparación** para actualizar el registro maestro.</span><span class="sxs-lookup"><span data-stu-id="3a880-173">In the **Compare Role User Master Record**, click **Complete comparison** to update the master record.</span></span> <span data-ttu-id="3a880-174">Cuando se le pida para guardar el rol, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3a880-174">When prompted to save the role, click **Yes**.</span></span>  
  
13. <span data-ttu-id="3a880-175">Guardar y salir.</span><span class="sxs-lookup"><span data-stu-id="3a880-175">Save and exit.</span></span>  
  
<span data-ttu-id="3a880-176">Comprobación de la instalación de RFC personalizada</span><span class="sxs-lookup"><span data-stu-id="3a880-176">Verifying Custom RFC Installation</span></span>  
 <span data-ttu-id="3a880-177">Después de instalar las RFC personalizadas, puede comprobar si la RFC se ha instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a880-177">After you install the custom RFCs, you can verify whether the RFCs installed correctly.</span></span>  
  
-   <span data-ttu-id="3a880-178">RFC Z_EXECUTE_SAP_QUERY, puede hacerlo mediante la ejecución de una consulta predefinida en el sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a880-178">For Z_EXECUTE_SAP_QUERY RFC, you can do so by executing a pre-defined query in SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="3a880-179">RFC Z_EXTRACT_DATA_OO, puede hacerlo mediante la realización de las siguientes pruebas para confirmar que la RFC funciona y está lista para su uso en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3a880-179">For Z_EXTRACT_DATA_OO RFC, you can do so by performing the following tests to confirm that the RFC operates and is ready for use in your system.</span></span>  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a><span data-ttu-id="3a880-180">Para probar la instalación de Z_EXTRACT_DATA_OO</span><span class="sxs-lookup"><span data-stu-id="3a880-180">To test the installation of Z_EXTRACT_DATA_OO</span></span>  
  
1.  <span data-ttu-id="3a880-181">En las herramientas de administración de autorización de GUI de SAP, ejecute SE37, módulo de función Z_EXTRACT_DATA_OO, y, a continuación, ejecute la solicitud de cambio en el modo de prueba presionando `F8`.</span><span class="sxs-lookup"><span data-stu-id="3a880-181">In the SAP GUI authorization administration tools, execute SE37, function module Z_EXTRACT_DATA_OO, and then run the RFC in test mode by pressing `F8`.</span></span> <span data-ttu-id="3a880-182">Rellenar los parámetros como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a880-182">Populate the parameters as follows.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="3a880-183">IN_METADATA_ONLY</span><span class="sxs-lookup"><span data-stu-id="3a880-183">IN_METADATA_ONLY</span></span>||  
    |<span data-ttu-id="3a880-184">IN_METADATA_LANGUAGE</span><span class="sxs-lookup"><span data-stu-id="3a880-184">IN_METADATA_LANGUAGE</span></span>|<span data-ttu-id="3a880-185">EN</span><span class="sxs-lookup"><span data-stu-id="3a880-185">EN</span></span>|  
    |<span data-ttu-id="3a880-186">IN_FROM_TABLE</span><span class="sxs-lookup"><span data-stu-id="3a880-186">IN_FROM_TABLE</span></span>|<span data-ttu-id="3a880-187">T000</span><span class="sxs-lookup"><span data-stu-id="3a880-187">T000</span></span>|  
    |<span data-ttu-id="3a880-188">IN_OUTPUT_MODE</span><span class="sxs-lookup"><span data-stu-id="3a880-188">IN_OUTPUT_MODE</span></span>|<span data-ttu-id="3a880-189">S</span><span class="sxs-lookup"><span data-stu-id="3a880-189">S</span></span>|  
    |<span data-ttu-id="3a880-190">IN_OUTPUT_FILENAME</span><span class="sxs-lookup"><span data-stu-id="3a880-190">IN_OUTPUT_FILENAME</span></span>||  
    |<span data-ttu-id="3a880-191">IN_USE_FIELD_EXITS</span><span class="sxs-lookup"><span data-stu-id="3a880-191">IN_USE_FIELD_EXITS</span></span>|<span data-ttu-id="3a880-192">X</span><span class="sxs-lookup"><span data-stu-id="3a880-192">X</span></span>|  
    |<span data-ttu-id="3a880-193">IN_SET_ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="3a880-193">IN_SET_ROWCOUNT</span></span>|<span data-ttu-id="3a880-194">0</span><span class="sxs-lookup"><span data-stu-id="3a880-194">0</span></span>|  
    |<span data-ttu-id="3a880-195">IN_DELIMITER</span><span class="sxs-lookup"><span data-stu-id="3a880-195">IN_DELIMITER</span></span>||  
    |<span data-ttu-id="3a880-196">IN_PACKET_SIZE</span><span class="sxs-lookup"><span data-stu-id="3a880-196">IN_PACKET_SIZE</span></span>|<span data-ttu-id="3a880-197">50,000</span><span class="sxs-lookup"><span data-stu-id="3a880-197">50,000</span></span>|  
    |<span data-ttu-id="3a880-198">IN_MAX_WRITE_ATTEMPTS</span><span class="sxs-lookup"><span data-stu-id="3a880-198">IN_MAX_WRITE_ATTEMPTS</span></span>|<span data-ttu-id="3a880-199">4</span><span class="sxs-lookup"><span data-stu-id="3a880-199">4</span></span>|  
    |<span data-ttu-id="3a880-200">IN_RETRY_DELAY</span><span class="sxs-lookup"><span data-stu-id="3a880-200">IN_RETRY_DELAY</span></span>|<span data-ttu-id="3a880-201">30</span><span class="sxs-lookup"><span data-stu-id="3a880-201">30</span></span>|  
    |<span data-ttu-id="3a880-202">IN_SQL_DATES_ON</span><span class="sxs-lookup"><span data-stu-id="3a880-202">IN_SQL_DATES_ON</span></span>||  
  
2.  <span data-ttu-id="3a880-203">Haga clic en **Execute** o presione `F8`.</span><span class="sxs-lookup"><span data-stu-id="3a880-203">Click **Execute** or press `F8`.</span></span>  
  
3.  <span data-ttu-id="3a880-204">En el panel de resultados, compruebe lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3a880-204">In the results pane, check the following.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="3a880-205">OUT_TABLEHEADER</span><span class="sxs-lookup"><span data-stu-id="3a880-205">OUT_TABLEHEADER</span></span>|<span data-ttu-id="3a880-206">\<Metadatos generales T000\></span><span class="sxs-lookup"><span data-stu-id="3a880-206">\<T000 general metadata\></span></span>|  
    |<span data-ttu-id="3a880-207">OUT_TECHNICALSETTINGS</span><span class="sxs-lookup"><span data-stu-id="3a880-207">OUT_TECHNICALSETTINGS</span></span>|<span data-ttu-id="3a880-208">\<Metadatos de nivel de base de datos técnica T000\></span><span class="sxs-lookup"><span data-stu-id="3a880-208">\<T000 technical database level metadata\></span></span>|  
    |<span data-ttu-id="3a880-209">OUT_RECORDLENGTH</span><span class="sxs-lookup"><span data-stu-id="3a880-209">OUT_RECORDLENGTH</span></span>|<span data-ttu-id="3a880-210">\<depende de versión SAP\></span><span class="sxs-lookup"><span data-stu-id="3a880-210">\<depends on SAP version\></span></span>|  
    |<span data-ttu-id="3a880-211">OUT_RECORDCOUNT</span><span class="sxs-lookup"><span data-stu-id="3a880-211">OUT_RECORDCOUNT</span></span>|<span data-ttu-id="3a880-212">\<Confirme el número de clientes en el sistema con SE16 en T000\></span><span class="sxs-lookup"><span data-stu-id="3a880-212">\<confirm the number of clients in your system with SE16 on T000\></span></span>|  
    |<span data-ttu-id="3a880-213">OUT_ZDATATABLE</span><span class="sxs-lookup"><span data-stu-id="3a880-213">OUT_ZDATATABLE</span></span>|<span data-ttu-id="3a880-214">\<confirmar este resultado con los datos de origen con 16 SAR en T000\></span><span class="sxs-lookup"><span data-stu-id="3a880-214">\<confirm this result with the source data using SE 16 on T000\></span></span>|  
    |<span data-ttu-id="3a880-215">OUT_RETURN_TAB</span><span class="sxs-lookup"><span data-stu-id="3a880-215">OUT_RETURN_TAB</span></span>|<span data-ttu-id="3a880-216">S 001 correcto</span><span class="sxs-lookup"><span data-stu-id="3a880-216">S 001 Success</span></span>|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a><span data-ttu-id="3a880-217">Quite la solicitud de cambio para el proveedor de datos para SAP</span><span class="sxs-lookup"><span data-stu-id="3a880-217">Remove the RFC for the Data Provider for SAP</span></span>  
  
1.  <span data-ttu-id="3a880-218">En el Explorador de objetos de GUI de SAP (SE80), busque todos los objetos con la clase de desarrollo ZMSBI.</span><span class="sxs-lookup"><span data-stu-id="3a880-218">In the SAP GUI Object Navigator (SE80), find all the objects with the ZMSBI development class.</span></span>  
  
2.  <span data-ttu-id="3a880-219">Eliminar todos los objetos con la clase de desarrollo ZMSBI de las siguientes carpetas de objetos de diccionario:</span><span class="sxs-lookup"><span data-stu-id="3a880-219">Delete all objects with the ZMSBI development class from the following Dictionary Objects folders:</span></span>  
  
    -   <span data-ttu-id="3a880-220">Estructuras</span><span class="sxs-lookup"><span data-stu-id="3a880-220">Structures</span></span>  
  
    -   <span data-ttu-id="3a880-221">Grupos de funciones</span><span class="sxs-lookup"><span data-stu-id="3a880-221">Function Groups</span></span>  
  
    -   <span data-ttu-id="3a880-222">Objeto autorizado</span><span class="sxs-lookup"><span data-stu-id="3a880-222">Authorized Object</span></span>  
  
3.  <span data-ttu-id="3a880-223">Generar un transporte y migrar a través de cada sistema donde se instaló una solicitud de cambio (por ejemplo, los sistemas desarrollo, prueba y producción).</span><span class="sxs-lookup"><span data-stu-id="3a880-223">Raise a transport, and migrate it through each system where you installed an RFC (development, test, and production systems, for example).</span></span>  
  
     <span data-ttu-id="3a880-224">Para obtener más ayuda, póngase en contacto con el Administrador de base de SAP.</span><span class="sxs-lookup"><span data-stu-id="3a880-224">For further assistance, contact your SAP Basis Administrator.</span></span>  
     
## <a name="next"></a><span data-ttu-id="3a880-225">Siguiente</span><span class="sxs-lookup"><span data-stu-id="3a880-225">Next</span></span>
[<span data-ttu-id="3a880-226">Definición del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="3a880-226">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[<span data-ttu-id="3a880-227">Tutoriales del adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="3a880-227">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)