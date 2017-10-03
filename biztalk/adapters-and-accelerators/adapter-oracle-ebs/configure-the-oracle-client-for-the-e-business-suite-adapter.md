---
title: Configurar el cliente de Oracle para el adaptador de E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 842b6ecc-5334-4cc0-af10-baa7f692ad23
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ada64bf6f54c95f3d6e1c8f968a506476dbbc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a><span data-ttu-id="3e5b8-102">Configurar al cliente de Oracle para el adaptador de E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="3e5b8-102">Configure the Oracle client for the E-Business Suite adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="3e5b8-103">En este tema solo es pertinente si utilizas tnsnames.ora para conectarse a la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="3e5b8-104">Para establecer una conexión con el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], el adaptador se conecta a la base de datos de Oracle subyacente a través del cliente de Oracle instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-104">To establish a connection to the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], the adapter connects to the underlying Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="3e5b8-105">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa el nombre de servicio de red que especifique en el URI de conexión para el cliente de Oracle para establecer una conexión a Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to Oracle E-Business Suite.</span></span> <span data-ttu-id="3e5b8-106">El nombre de servicio de red es un alias que utiliza el cliente de Oracle para adquirir la información de conexión para el destino de servicio de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="3e5b8-107">El cliente de Oracle resuelve el servicio de net nombre según el método de asignación de nombres que está configurado para usar.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="3e5b8-108">Utilice Oracle Net Configuration Assistant para configurar los métodos de asignación de nombres que va a usar el cliente de Oracle.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="3e5b8-109">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con el método de nomenclatura Local para conectarse a Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-109">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports the Local Naming method for connecting to Oracle E-Business Suite.</span></span> <span data-ttu-id="3e5b8-110">Este método usa un archivo local, tnsnames.ora, para resolver el nombre de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="3e5b8-111">El archivo tnsnames.ora asocia nombres de servicio de red con conexión descriptores que contienen la información que necesita el cliente de Oracle para establecer una conexión a un servicio específico de base de datos de Oracle (instancia).</span><span class="sxs-lookup"><span data-stu-id="3e5b8-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information that the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="3e5b8-112">El siguiente es un ejemplo de entrada de tnsnames.ora.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
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
  
 <span data-ttu-id="3e5b8-113">En esta entrada de ejemplo, el adaptador es el nombre de servicio de red.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="3e5b8-114">El descriptor de conexión especifica información de dirección y el nombre de servicio del servicio de base de datos de Oracle asociado con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="3e5b8-115">Puede usar Oracle Net Configuration Assistant para crear y configurar los nombres de servicio de red en tnsnames.ora.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="3e5b8-116">Después de haber configurado el nombre de servicio de red, puede especificar en un URI de conexión como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracleebs://ADAPTER  
```  
  
 <span data-ttu-id="3e5b8-117">Para obtener más información sobre el uso de Oracle Net Configuration Assistant y tnsnames.ora, consulte el Oracle base de datos neto servicios Guía del administrador.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="3e5b8-118">Consulte al administrador de base de datos acerca de los detalles de configuración para su instalación específica.</span><span class="sxs-lookup"><span data-stu-id="3e5b8-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5b8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e5b8-119">See Also</span></span>  
 [<span data-ttu-id="3e5b8-120">Crear una conexión a Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="3e5b8-120">Create a connection to Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)