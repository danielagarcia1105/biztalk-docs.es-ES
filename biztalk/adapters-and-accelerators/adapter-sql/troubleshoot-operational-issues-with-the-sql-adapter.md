---
title: Solucionar problemas de funcionamiento con el adaptador SQL en BizTalk | Microsoft Docs
description: Problemas comunes y soluciones para el adaptador de SQL en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb3f48fca23825ec98fdc7f38012e44f7b2a00e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994589"
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a><span data-ttu-id="c6d7f-103">Solucionar problemas de funcionamiento con el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="c6d7f-103">Troubleshoot Operational Issues with the SQL adapter</span></span>
<span data-ttu-id="c6d7f-104">En esta sección se analiza el uso de técnicas de solución de problemas para resolver errores operativos que pueden surgir al usar [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="c6d7f-105">La habilitación del seguimiento</span><span class="sxs-lookup"><span data-stu-id="c6d7f-105">Enabling Tracing</span></span>  
 <span data-ttu-id="c6d7f-106">Debe habilitar el seguimiento entre el adaptador, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], y SQL Server para recopilar más información acerca de los problemas que encuentre al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-106">You must enable tracing between the adapter, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and SQL Server to gather more information about any issues you encounter while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="c6d7f-107">Para obtener más información acerca del seguimiento de soporte técnico en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes en el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-107">For more information about tracing support in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Diagnostic Tracing and Message Logging in the SQL adapter](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="c6d7f-108">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="c6d7f-108">Known Issues</span></span>  
 <span data-ttu-id="c6d7f-109">Los siguientes son los errores más comunes que pueden surgir al usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], junto con su causa y resolución.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-109">The following are the most common errors you might encounter when using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a> <span data-ttu-id="c6d7f-110">Error al cargar los enlaces del adaptador</span><span class="sxs-lookup"><span data-stu-id="c6d7f-110">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="c6d7f-111">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-111">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-112">Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], obtendrá el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6d7f-112">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="c6d7f-113">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-113">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-114">Al intentar iniciar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-114">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="c6d7f-115">A su vez, los enlaces del adaptador dependen del software cliente específica de la aplicación de empresa.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-115">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="c6d7f-116">Es posible que con este problema si realizó una instalación típica o completo del adaptador, que se instala en todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-116">You might face this issue if you did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="c6d7f-117">Sin embargo, podrían instalarse las bibliotecas de cliente de línea de negocio para sólo una aplicación empresarial.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-117">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="c6d7f-118">Como resultado, la interfaz gráfica de usuario no se puede cargar los enlaces para los demás adaptadores.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-118">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="c6d7f-119">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-119">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-120">Asegúrese de que realizar una instalación personalizada de los adaptadores que se va a instalar a sólo el adaptador que necesita.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-120">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SQLDisplay"></a> <span data-ttu-id="c6d7f-121">El adaptador de SQL no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c6d7f-121">The SQL adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="c6d7f-122">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-122">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-123">A diferencia de la versión anterior de los adaptadores incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no se muestra en la lista de adaptadores en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-123">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="c6d7f-124">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-124">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-125">La versión más reciente [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace personalizado de WCF.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-125">The latest [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="c6d7f-126">Por lo tanto, aunque el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no muestra basada en WCF [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-126">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="c6d7f-127">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-127">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-128">Puede agregar explícitamente la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregación del adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-128">You can explicitly add the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_MissingAction"></a> <span data-ttu-id="c6d7f-129">Error al realizar operaciones en una base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6d7f-129">Error while performing operations on a SQL Server database</span></span>  
 <span data-ttu-id="c6d7f-130">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-130">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-131">El adaptador produce el siguiente error al realizar cualquier operación en una base de datos de SQL Server mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-131">The adapter gives the following error when performing any operation on a SQL Server database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="c6d7f-132">**Para que BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-132">**For BizTalk Server**</span></span>  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  <span data-ttu-id="c6d7f-133">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-133">**Cause**</span></span>  
  
  <span data-ttu-id="c6d7f-134">No se especifica la acción de WCF para el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-134">The WCF action for the message is not specified.</span></span> <span data-ttu-id="c6d7f-135">WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador de la operación que se realizará en la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-135">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
  <span data-ttu-id="c6d7f-136">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-136">**Resolution**</span></span>  
  
  <span data-ttu-id="c6d7f-137">Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-137">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="c6d7f-138">Para obtener instrucciones, consulte [configurar la acción SOAP para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-138">For instructions, see [Configure the SOAP action for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span></span> <span data-ttu-id="c6d7f-139">Consulte [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) para ver una lista de acciones para cada operación.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-139">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SQLInvalidOp"></a> <span data-ttu-id="c6d7f-140">InvalidOperationException con ErrorCode = 5 al realizar operaciones de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c6d7f-140">InvalidOperationException with ErrorCode=5 while performing FILESTREAM operations</span></span>  
 <span data-ttu-id="c6d7f-141">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-141">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-142">Obtiene el siguiente error mientras usa la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar operaciones de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-142">You get the following error while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform FILESTREAM operations.</span></span>  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 <span data-ttu-id="c6d7f-143">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-143">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-144">Puede que haya especificado las credenciales de base de datos para conectarse a la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-144">You might have specified database credentials to connect to the SQL Server database.</span></span> <span data-ttu-id="c6d7f-145">Para llevar a cabo operaciones de FILESTREAM, siempre debe utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-145">To perform FILESTREAM operations, you must always use Windows Authentication.</span></span> <span data-ttu-id="c6d7f-146">El código de error "5" indica que se deniega el acceso debido a credenciales incorrectas.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-146">The error code “5” denotes that access is denied because of incorrect credentials.</span></span> <span data-ttu-id="c6d7f-147">Para obtener más información acerca de los códigos de error diferentes, consulte [códigos de Error del sistema (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-147">For more information about the different error codes, see [System Error Codes (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx).</span></span>
  
 <span data-ttu-id="c6d7f-148">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-148">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-149">Usar la autenticación de Windows para conectarse a la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-149">Use Windows Authentication to connect to the SQL Server database.</span></span> <span data-ttu-id="c6d7f-150">En [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede hacerlo si se deja al usuario campos de nombre y la contraseña en blanco en el cuadro de diálogo de configuración de puerto de WCF-Custom o WCF-SQL.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-150">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can do so by leaving the user name and password fields blank in the WCF-Custom or WCF-SQL port configuration dialog box.</span></span>  
  
###  <a name="BKMK_SQLPolling"></a> <span data-ttu-id="c6d7f-151">Sondear la operación no devuelve ningún mensaje incluso si se especifican las instrucciones válidas para PollingStatement y PolledDataAvailableStatement</span><span class="sxs-lookup"><span data-stu-id="c6d7f-151">Polling operation does not return any messages even if valid statements are specified for PollingStatement and PolledDataAvailableStatement</span></span>  
 <span data-ttu-id="c6d7f-152">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-152">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-153">Incluso si se especifican los valores válidos para las propiedades de enlace PollingStatement y PolledDataAvailableStatement, el adaptador no recibe un mensaje de sondeo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-153">Even if valid values are specified for the PollingStatement and PolledDataAvailableStatement binding properties, the adapter does not receive a polling message from SQL Server.</span></span>  
  
 <span data-ttu-id="c6d7f-154">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-154">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-155">Compruebe si otra transacción ha tomado un bloqueo en la tabla que el adaptador es el sondeo.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-155">Verify whether any other transaction has taken a lock on the table that the adapter is polling.</span></span>  
  
 <span data-ttu-id="c6d7f-156">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-156">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-157">Si desea sondear una tabla que se está actualizando como parte de otra transacción, puede usar el parámetro "with (nolock)" como parte de la consulta especificada para la propiedad de enlace PolledDataAvailableStatement para asegurarse de que se devuelven datos incluso si se impone un bloqueo la otra transacción.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-157">If you want to poll a table that is being updated as part of another transaction, you can consider using “with (nolock)” parameter as part of the query specified for PolledDataAvailableStatement binding property to ensure that data is returned even if a lock is imposed by the other transaction.</span></span> <span data-ttu-id="c6d7f-158">Para obtener más información, consulte [el bloqueo de SQL en el motor de base de datos](https://msdn.microsoft.com/library/ms190615.aspx).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-158">For more information, see [SQL Locking in the Database Engine](https://msdn.microsoft.com/library/ms190615.aspx).</span></span>
  
###  <a name="BKMK_SQLSingleOp"></a> <span data-ttu-id="c6d7f-159">Se produce un error en el adaptador Insertar, actualizar o eliminar grandes volúmenes de datos en una sola operación mediante BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c6d7f-159">The adapter fails to insert, update, or delete large volumes of data in a single operation using BizTalk Server</span></span>  
 <span data-ttu-id="c6d7f-160">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-160">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-161">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no se puede insertar, actualizar o eliminar grandes volúmenes de datos en una única operación utilizando [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-161">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] fails to insert, update, or delete large volumes of data in a single operation using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c6d7f-162">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-162">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-163">Insertar, actualizar o eliminar grandes volúmenes de datos puede tardar tiempo y el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] o la transacción en el que se realiza la operación, puede agotar el tiempo.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-163">Inserting, updating, or deleting large volumes of data may take time and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] or the transaction in which the operation is being performed, may time out.</span></span>  
  
 <span data-ttu-id="c6d7f-164">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-164">**Resolution**</span></span>  
  
- <span data-ttu-id="c6d7f-165">**Para que BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-165">**For BizTalk Server**</span></span>  
  
  1. <span data-ttu-id="c6d7f-166">Especifique el tiempo de espera para el adaptador de WCF en el archivo machine.config. Navegue hasta el archivo machine.config en \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG y agregue el fragmento que es similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-166">Specify the timeout for the WCF adapter in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
     ```  
     <configuration>  
      <system.transactions>  
       <machineSettings maxTimeout="02:00:00" />  
      </system.transactions>  
     </configuration>  
     ```  
  
      <span data-ttu-id="c6d7f-167">Con esta configuración, el tiempo de espera del adaptador WCF se establece en 2 horas.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-167">With this setting, the WCF adapter timeout is set to 2 hours.</span></span>  
  
  2. <span data-ttu-id="c6d7f-168">Especifique la configuración de tiempo de espera para las transacciones de MSDTC en el archivo machine.config. Navegue hasta el archivo machine.config en \<unidadDelSistema\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG y agregue el fragmento que es similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-168">Specify the timeout settings for MSDTC transactions in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
     ```  
     <system.transactions>   
             <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
         </system.transactions>  
  
     ```  
  
      <span data-ttu-id="c6d7f-169">Con esta configuración, el tiempo de espera MSDTC se establece en 2 horas.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-169">With this setting, the MSDTC timeout is set to 2 hours.</span></span> <span data-ttu-id="c6d7f-170">El valor predeterminado de tiempo de espera MSDTC es 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-170">The default value for MSDTC timeout is 10 minutes.</span></span>  
  
     > [!IMPORTANT]
     >  <span data-ttu-id="c6d7f-171">Debe realizar este cambio en los equipos que ejecutan el cliente del adaptador y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-171">You must make this change on the computers running the adapter client and SQL Server.</span></span> <span data-ttu-id="c6d7f-172">En el extracto, reemplace < nombre_equipo > por el nombre del equipo que ejecuta el cliente de adaptador y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-172">In the excerpt, replace <computer_name> with the name of computer running the adapter client and SQL Server.</span></span>  
  
  3. <span data-ttu-id="c6d7f-173">Establecer el **SendTimeout** enlaza la propiedad para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en un valor bastante grande.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-173">Set the **SendTimeout** binding property for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to a fairly large value.</span></span> <span data-ttu-id="c6d7f-174">Para obtener instrucciones sobre cómo establecer las propiedades de enlace, consulte [configurar las propiedades de enlace del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-174">For instructions on how to set the binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a> <span data-ttu-id="c6d7f-175">Se produce un error de validación del esquema completo en BizTalk Server para los mensajes de respuesta que contiene el conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="c6d7f-175">Full schema validation in BizTalk Server fails for response messages containing DataSet</span></span>  
 <span data-ttu-id="c6d7f-176">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-176">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-177">Para las operaciones que devuelven un mensaje de respuesta que contiene un conjunto de datos, por ejemplo ExecuteReader, validación de esquema completo se produce un error en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-177">For operations that return a response message containing a DataSet, for example ExecuteReader, full schema validation fails in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c6d7f-178">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-178">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-179">Se recomienda no realizar una validación del esquema completo para los mensajes de respuesta que contiene un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-179">We recommend you to not do a full schema validation for response messages containing a dataset.</span></span> <span data-ttu-id="c6d7f-180">En su lugar, podría hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6d7f-180">Instead, you could do the following:</span></span>  
  
1.  <span data-ttu-id="c6d7f-181">Ejecute la operación una vez devuelve el mensaje de respuesta con el esquema.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-181">Execute the operation once that returns the response message with the schema.</span></span>  
  
2.  <span data-ttu-id="c6d7f-182">Copie el esquema del mensaje de respuesta a un archivo .xsd y agregue este archivo al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-182">Copy the schema from the response message to a .xsd file and add this file to your BizTalk project.</span></span>  
  
3.  <span data-ttu-id="c6d7f-183">Usar una consulta xpath en la orquestación para extraer los datos del mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-183">Use an xpath query in your orchestration to extract the data from the response message.</span></span>  
  
###  <a name="BKMK_SQLRootNode"></a> <span data-ttu-id="c6d7f-184">Error con RootNode TypeName en proyectos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="c6d7f-184">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="c6d7f-185">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-185">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-186">En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :</span><span class="sxs-lookup"><span data-stu-id="c6d7f-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="c6d7f-187">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="c6d7f-188">Haga clic en el nodo raíz al que hace referencia en el error y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c6d7f-189">Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o palabras reservadas, por ejemplo, punto (.).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a> <span data-ttu-id="c6d7f-190">Se produce un error de adaptador generar los metadatos de los procedimientos almacenados fuertemente tipados con tablas temporales</span><span class="sxs-lookup"><span data-stu-id="c6d7f-190">Adapter fails to generate metadata of strongly-typed stored procedure with temporary tables</span></span>  
 <span data-ttu-id="c6d7f-191">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-191">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-192">Se produce un error en el adaptador generar metadatos para los procedimientos almacenados fuertemente tipados que incluyen tablas temporales en su definición.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-192">The adapter fails to generate metadata for strongly-typed stored procedures that include temporary tables in their definition.</span></span> <span data-ttu-id="c6d7f-193">El adaptador proporciona la siguiente excepción.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-193">The adapter gives the following exception.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 <span data-ttu-id="c6d7f-194">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-194">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-195">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite la generación de metadatos para los procedimientos almacenados fuertemente tipadas que contienen las tablas temporales en su definición.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-195">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support generating metadata for strongly-typed stored procedures that contain temporary tables in their definition.</span></span> <span data-ttu-id="c6d7f-196">En su lugar, debe generar metadatos para el mismo procedimiento en el **procedimientos** nodo mientras usa la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-196">Instead, you should generate metadata for the same procedure from under the **Procedures** node while using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
###  <a name="BKMK_SQLVS2008"></a> <span data-ttu-id="c6d7f-197">Advertencia de enlace no válido al usar el adaptador en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c6d7f-197">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="c6d7f-198">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-198">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-199">Cuando se utiliza el adaptador para crear una aplicación en Visual Studio y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6d7f-199">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="c6d7f-200">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-200">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-201">Esta advertencia aparece porque la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enlace, `sqlBinding`, no un enlace estándar incluye el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6d7f-201">This warning appears because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding, `sqlBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="c6d7f-202">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-202">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-203">Puede omitir esta advertencia de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-203">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_SQLNotification"></a> <span data-ttu-id="c6d7f-204">BizTalk Server produce una excepción si usa más de un esquema de notificación en la misma aplicación o el esquema de notificación en varias aplicaciones en el mismo host</span><span class="sxs-lookup"><span data-stu-id="c6d7f-204">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="c6d7f-205">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-205">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-206">BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no puede encontrar la especificación de documento; varios esquemas coincidieron con el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-206">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="c6d7f-207">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-207">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-208">Esto sucede debido a una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6d7f-208">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="c6d7f-209">Ha generado más de un esquema de notificación en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para recibir notificaciones de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-209">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="c6d7f-210">Dado que los esquemas de notificaciones son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-210">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="c6d7f-211">En el caso de varios proyectos, han generado un esquema de notificación para cada uno de los proyectos, que se implementan cada proyecto para una aplicación de BizTalk Server independiente en el mismo host de BizTalk Server y, a continuación, ejecutó una aplicación o aplicaciones para recibir notificaciones de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-211">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="c6d7f-212">Dado que los ensamblados y esquemas son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en varias aplicaciones de BizTalk Server y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-212">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="c6d7f-213">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-213">**Resolution**</span></span>  
  
  <span data-ttu-id="c6d7f-214">Utilizar un único archivo de esquema de notificación para una aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-214">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="c6d7f-215">Si tiene que usar el esquema de notificación en varias aplicaciones de BizTalk Server en el mismo host, cree una aplicación que contenga un único esquema de notificación y, a continuación, utilice el esquema de notificación de todas las demás aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-215">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_SQLRestoreConn"></a> <span data-ttu-id="c6d7f-216">Cliente de adaptador produce una excepción de realizar una operación una vez restaurada la conectividad entre el cliente de adaptador y la base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6d7f-216">Adapter client throws an exception on performing an operation after the connectivity is restored between the adapter client and the SQL Server database</span></span>  
 <span data-ttu-id="c6d7f-217">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-217">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-218">Cliente de adaptador inicia la siguiente excepción al ejecutar una operación en la base de datos de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="c6d7f-218">Adapter client throws the following exception on executing an operation on the SQL Server database:</span></span>  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 <span data-ttu-id="c6d7f-219">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-219">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-220">Durante la ejecución de una operación, el adaptador usa la conexión de la agrupación de conexiones ADO.NET de SQL para conectarse a la base de datos de SQL Server y realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-220">During the execution of an operation, the adapter uses the connection from the SQL ADO.NET connection pool to connect to the SQL Server database, and perform the operation.</span></span> <span data-ttu-id="c6d7f-221">Si se produce una interrupción de red breves entre el cliente de adaptador y la base de datos de SQL Server o la base de datos de SQL Server está inactivo temporalmente, todas las conexiones de la agrupación de conexiones ADO.NET SQL dejan de ser válidas.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-221">If there is a brief network outage between the adapter client and the SQL Server database or if the SQL Server database is down temporarily, all the connections in the SQL ADO.NET connection pool become invalid.</span></span> <span data-ttu-id="c6d7f-222">Después de que se restaura la conectividad y vuelva a realizar una operación en la base de datos de SQL Server, el adaptador usa las mismas conexiones no válidas de la agrupación de conexiones ADO.NET de SQL y, por lo tanto, el cliente de adaptador produce la excepción.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-222">After the connectivity is restored and you try to perform an operation on the SQL Server database, the adapter uses the same invalid connections from the SQL ADO.NET connection pool, and therefore the adapter client throws the exception.</span></span>  
  
 <span data-ttu-id="c6d7f-223">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-223">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-224">El cliente del adaptador debe implementar la lógica de reintento en su ejecución de la operación donde debe detectar la excepción y especifique el número de reintentos de la operación como "n + 1", donde "n" es el valor especificado para la propiedad de enlace MaxConnectionPoolSize.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-224">The adapter client should implement retry logic in their operation execution where they should catch the exception and specify the operation retry count as “n+1”, where “n” is the value specified for the MaxConnectionPoolSize binding property.</span></span> <span data-ttu-id="c6d7f-225">Esto implica que si hay "n" número de conexiones en el grupo de conexiones que se han representado no válido, teóricamente, el adaptador cliente debería reintentar durante un máximo de "n + 1" veces para obtener una conexión válida y, por lo tanto, realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-225">This implies that if there are “n” number of connections in the connection pool that have been rendered invalid, theoretically the adapter client should retry for a maximum of “n+1” times to get a valid connection, and hence perform the operation.</span></span>  
  
 <span data-ttu-id="c6d7f-226">Por ejemplo, para especificar el reintento recuento [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], abra el **propiedades** cuadro de diálogo de un puerto de envío en una aplicación, haga clic en **opciones avanzadas de transporte** en el panel izquierdo del cuadro de diálogo y, en el **Opciones de transporte** área, especifique un valor en el **número de reintentos** lista.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-226">For example, to specify the retry count in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], open the **Properties** dialog box of a send port in an application, click **Transport Advanced Options** in the left pane of the dialog box, and in the **Transport Options** area, specify a value in the **Retry count** list.</span></span>  
  
###  <a name="BKMK_MemUsage"></a> <span data-ttu-id="c6d7f-227">Uso de memoria y subproceso recuento aumenta cuando se usa el adaptador en una operación de entrada con transacciones</span><span class="sxs-lookup"><span data-stu-id="c6d7f-227">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="c6d7f-228">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-228">**Problem**</span></span>  
  
 <span data-ttu-id="c6d7f-229">En una operación de entrada con transacciones, como el sondeo, **si no hay ningún dato disponible en la tabla que se sondea** y while sigue sondeando el adaptador, durante un período de tiempo experimente un aumento en el uso de memoria y el número de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-229">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="c6d7f-230">**Causa**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-230">**Cause**</span></span>  
  
 <span data-ttu-id="c6d7f-231">**Si no hay ningún dato disponible en la tabla que se sondea**, después cada ciclo de tiempo de espera de recepción [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] genera un subproceso nuevo para continuar la operación de sondeo.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-231">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="c6d7f-232">Por lo tanto, el uso de memoria y recuento de subprocesos aumenta durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-232">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="c6d7f-233">Sin embargo, si la tabla que se sondea tiene algunos datos, sigue el mismo subproceso realizar todos los sondeos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-233">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="c6d7f-234">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="c6d7f-234">**Resolution**</span></span>  
  
 <span data-ttu-id="c6d7f-235">Se recomienda establecer el **ReceiveTimeout** en el valor máximo posible, que es 24.20:31:23.6470000 (24 días) para que un nuevo subproceso se genera solo cada 24 días.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-235">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="c6d7f-236">Esto garantizará que el recuento de subprocesos y de uso de memoria no aumentan demasiado demasiado pronto.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-236">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6d7f-237">Si se ha establecido SqlAdapterInboundTransactionBehavior, asegúrese de que el TransactionTimeout también está configurado para el valor máximo posible, que es 24.20:31:23.6470000 (24 días).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-237">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="c6d7f-238">Cuando se usa esta solución alternativa, podemos agregar la SqlAdapterInboundTransactionBehavior sólo si el nivel de aislamiento de transacción debe estar configurada.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-238">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="c6d7f-239">En caso contrario, es una práctica recomendada para quitar ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-239">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="c6d7f-240">Para obtener más información sobre la **ReceiveTimeout** enlaza la propiedad, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-240">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="c6d7f-241">Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="c6d7f-241">For instructions on specifying binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6d7f-242">Al usar el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establecer el tiempo de espera en un valor grande no afecta a la funcionalidad del adaptador.</span><span class="sxs-lookup"><span data-stu-id="c6d7f-242">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d7f-243">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6d7f-243">See Also</span></span>  
[<span data-ttu-id="c6d7f-244">Solucionar problemas del adaptador SQL</span><span class="sxs-lookup"><span data-stu-id="c6d7f-244">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)