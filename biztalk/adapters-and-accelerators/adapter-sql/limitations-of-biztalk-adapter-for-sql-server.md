---
title: Limitaciones del adaptador de BizTalk para SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a80990a9e3f417b64a06d8823300d53b2c4f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222684"
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a><span data-ttu-id="d0dcb-102">Limitaciones del adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0dcb-102">Limitations of BizTalk Adapter for SQL Server</span></span>
<span data-ttu-id="d0dcb-103">Los siguientes son limitaciones para conocidas [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d0dcb-103">The following are known limitations for [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:</span></span>  
  
-   <span data-ttu-id="d0dcb-104">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no es compatible con los sinónimos creados en la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support synonyms created in the SQL Server database.</span></span> <span data-ttu-id="d0dcb-105">Para obtener información acerca de los sinónimos en SQL Server, vea [http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111).</span><span class="sxs-lookup"><span data-stu-id="d0dcb-105">For information about synonyms in SQL Server, see [http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111).</span></span>  
  
-   <span data-ttu-id="d0dcb-106">Si cambia la hora del sistema del equipo que ejecuta el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host, el tiempo no se actualiza automáticamente en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-106">If you change the system time of the computer running the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host, the time is not updated automatically in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host.</span></span> <span data-ttu-id="d0dcb-107">Esto podría provocar un comportamiento incorrecto de las operaciones de entrada que utilizan el puerto de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0dcb-107">This could lead to incorrect behavior of the inbound operations that use the receive port of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d0dcb-108">Como alternativa, debe reiniciar la instancia de host que tiene un puerto de recepción después de haber cambiado la hora del sistema del equipo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-108">As a workaround, you must restart the host instance that has a receive port after you have changed the system time of the computer running it.</span></span>  
  
-   <span data-ttu-id="d0dcb-109">Si un nombre de parámetro en un procedimiento almacenado contiene 127 o varios caracteres, no se puede ejecutar el procedimiento almacenado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0dcb-109">If a parameter name in a stored procedure contains 127 or more characters, you cannot execute the stored procedure using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="d0dcb-110">Esto es debido a la limitación de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-110">This is due to the limitation of ADO.NET.</span></span>  
  
-   <span data-ttu-id="d0dcb-111">El WSDL del [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] genera, cuando se convierte en un servidor proxy, expone la columna DateTimeOffset como System.DateTime.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-111">The WSDL the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] generates, when converted to a proxy, exposes the DateTimeOffset column as System.DateTime.</span></span> <span data-ttu-id="d0dcb-112">Este tipo de datos no puede almacenar información de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-112">This data type cannot store time zone information.</span></span> <span data-ttu-id="d0dcb-113">En consecuencia, cualquier valor de fecha y hora que el adaptador envía al servidor proxy se convertirán en hora local en la aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-113">As a consequence, any date/time value the adapter sends to the proxy will be converted into local time in the .NET application.</span></span> <span data-ttu-id="d0dcb-114">Si desea mantener la información de zona horaria, debe cambiar la interfaz del proxy para utilizar el tipo de cadena en lugar de System.DateTime.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-114">If you wish to keep the time zone information, you must change the interface of your proxy to use the String type instead of System.DateTime.</span></span> <span data-ttu-id="d0dcb-115">A continuación, utilice XmlConvert.ToDateTimeOffset para crear un objeto Sytstem.DateTimeOffset, que puede almacenar la información de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="d0dcb-115">Then, use XmlConvert.ToDateTimeOffset to create a Sytstem.DateTimeOffset object, which can store the timezone information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0dcb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0dcb-116">See Also</span></span>  
 [<span data-ttu-id="d0dcb-117">Comprender el adaptador de BizTalk para SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0dcb-117">UNderstand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)