---
title: Configurar el cliente de Oracle para el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- net service name
- tnsnames.ora
- configuring, the Oracle client
- connect descriptor
- Oracle client, configuring
- Oracle Net Configuration Assistant
- Oracle Net Configuration Assistant, using the
ms.assetid: 2d4c0f20-b3a6-453f-a9b3-65fd5a38c020
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 209d5603a9f8ff8c09185093efb976afb6432d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a><span data-ttu-id="ac422-102">Configurar al cliente de Oracle para el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ac422-102">Configure the Oracle Client for the Oracle Database adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="ac422-103">En este tema solo es pertinente si utilizas tnsnames.ora para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ac422-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="ac422-104">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] se conecta a la base de datos de Oracle a través del cliente de Oracle instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ac422-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] connects to the Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="ac422-105">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] pasa el nombre de servicio de red que especifique en el URI de conexión para el cliente de Oracle para establecer una conexión a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ac422-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to the Oracle database.</span></span> <span data-ttu-id="ac422-106">El nombre de servicio de red es un alias que utiliza el cliente de Oracle para adquirir la información de conexión para el destino de servicio de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ac422-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="ac422-107">El cliente de Oracle resuelve el servicio de net nombre según el método de asignación de nombres que está configurado para usar.</span><span class="sxs-lookup"><span data-stu-id="ac422-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="ac422-108">Utilice Oracle Net Configuration Assistant para configurar los métodos de asignación de nombres que va a usar el cliente de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ac422-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="ac422-109">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con el método de nomenclatura Local para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ac422-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the Local Naming method for connecting to the Oracle database.</span></span> <span data-ttu-id="ac422-110">Este método usa un archivo local, tnsnames.ora, para resolver el nombre de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="ac422-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="ac422-111">La asociación de archivo tnsnames.ora nombres de servicio de red con conexión descriptores que contienen la información que necesita el cliente de Oracle para establecer una conexión a un servicio específico de base de datos de Oracle (instancia).</span><span class="sxs-lookup"><span data-stu-id="ac422-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="ac422-112">El siguiente es un ejemplo de entrada de tnsnames.ora.</span><span class="sxs-lookup"><span data-stu-id="ac422-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
```  
ADAPTER =  
  (DESCRIPTION =  
    (ADDRESS_LIST =  
      (ADDRESS = (PROTOCOL = TCP)(HOST = yourOracleServer)(PORT = 1521))  
    )  
    (CONNECT_DATA =  
      (SERVICE_NAME = yourOracleDatabaseServiceName)  
    )  
  )  
```  
  
 <span data-ttu-id="ac422-113">En esta entrada de ejemplo, el adaptador es el nombre de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="ac422-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="ac422-114">El descriptor de conexión especifica información de dirección y el nombre de servicio del servicio de base de datos de Oracle asociado con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="ac422-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="ac422-115">Puede usar Oracle Net Configuration Assistant para crear y configurar los nombres de servicio de red en tnsnames.ora.</span><span class="sxs-lookup"><span data-stu-id="ac422-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="ac422-116">Después de haber configurado el nombre de servicio de red, puede especificar en un URI de conexión como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ac422-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracledb://ADAPTER  
```  
  
 <span data-ttu-id="ac422-117">Para obtener más información sobre el uso de Oracle Net Configuration Assistant y tnsnames.ora, consulte el Oracle base de datos neto servicios Guía del administrador.</span><span class="sxs-lookup"><span data-stu-id="ac422-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="ac422-118">Consulte al administrador de base de datos acerca de los detalles de configuración para su instalación específica.</span><span class="sxs-lookup"><span data-stu-id="ac422-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac422-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac422-119">See Also</span></span>  
[<span data-ttu-id="ac422-120">Crear una conexión a la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ac422-120">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)