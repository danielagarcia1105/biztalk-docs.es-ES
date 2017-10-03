---
title: Servidor secreto principal | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d02d5608546e86801bfc4a2281c42f902594e79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="master-secret-server"></a><span data-ttu-id="d84dd-102">Servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="d84dd-102">Master Secret Server</span></span>
<span data-ttu-id="d84dd-103">El servidor secreto principal es el servidor de inicio de sesión único empresarial (SSO) que almacena el secreto principal (clave de cifrado).</span><span class="sxs-lookup"><span data-stu-id="d84dd-103">The master secret server is the Enterprise Single Sign-On (SSO) server that stores the master secret (encryption key).</span></span> <span data-ttu-id="d84dd-104">Este servidor genera el secreto principal cuando lo solicita un administrador de SSO</span><span class="sxs-lookup"><span data-stu-id="d84dd-104">The master secret server generates the master secret when an SSO administrator requests it.</span></span> <span data-ttu-id="d84dd-105">y lo almacena cifrado en el Registro.</span><span class="sxs-lookup"><span data-stu-id="d84dd-105">The master secret server stores the encrypted master secret in the registry.</span></span> <span data-ttu-id="d84dd-106">Sólo los administradores de inicio de sesión único pueden obtener acceso al secreto principal.</span><span class="sxs-lookup"><span data-stu-id="d84dd-106">Only Single Sign-On administrators can access the master secret.</span></span>  
  
 <span data-ttu-id="d84dd-107">Los demás servidores de inicio de sesión único comprueban cada 30 segundos si ha cambiado el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="d84dd-107">The other Single Sign-On servers check every 30 seconds to see whether the master secret has changed.</span></span> <span data-ttu-id="d84dd-108">Si ha cambiado, lo leen de forma protegida; de lo contrario, continúan usando el secreto principal que tienen almacenado en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d84dd-108">If it has changed, they read it securely; otherwise, they continue to use the master secret they already have cached in memory.</span></span> <span data-ttu-id="d84dd-109">El servicio SSO utiliza el secreto principal para cifrar y descifrar las credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="d84dd-109">The SSO service uses the master secret to encrypt and decrypt the user credentials.</span></span>  
  
 <span data-ttu-id="d84dd-110">No puede usar el sistema SSO hasta que un administrador de SSO configure el servidor secreto principal y genere el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="d84dd-110">You cannot use the SSO system until an SSO administrator configures the master secret server and generates the master secret.</span></span> <span data-ttu-id="d84dd-111">El servidor secreto principal genera el secreto principal durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="d84dd-111">The master secret server generates the master secret during configuration.</span></span> <span data-ttu-id="d84dd-112">Sólo los administradores de SSO pueden generar el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="d84dd-112">Only SSO administrators can generate the master secret.</span></span> <span data-ttu-id="d84dd-113">Un administrador de SSO debe configurar el servidor secreto principal y la base de datos de SSO para que las aplicaciones puedan usar el servicio SSO.</span><span class="sxs-lookup"><span data-stu-id="d84dd-113">An SSO administrator must configure the master secret server and the SSO database before an application can use the SSO service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d84dd-114">Tras generar el secreto principal, se recomienda encarecidamente realizar una copia de seguridad y almacenarla en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="d84dd-114">After you generate the master secret, it is strongly recommended that you back it up and store it in a secure location.</span></span>  
  
 <span data-ttu-id="d84dd-115">Cuando un administrador de SSO tiene que generar el secreto principal (por ejemplo, si el administrador de SSO desea cambiar el secreto principal periódicamente), el servidor secreto principal almacena tanto el secreto principal antiguo como el nuevo.</span><span class="sxs-lookup"><span data-stu-id="d84dd-115">When an SSO administrator needs to regenerate the master secret, for example, if the SSO administrator wants to change the master secret periodically, the master secret server stores both the old and new master secret.</span></span> <span data-ttu-id="d84dd-116">El servidor secreto principal pasa después por todas las asignaciones, las descifra con el secreto principal antiguo y las vuelve a cifrar con el secreto principal nuevo.</span><span class="sxs-lookup"><span data-stu-id="d84dd-116">The master secret server then goes through all the mappings, decrypts them using the old master secret, and encrypts them again using the new master secret.</span></span>  
  
 <span data-ttu-id="d84dd-117">Si el servidor secreto principal da error, todas las operaciones de tiempo de ejecución que se estén ejecutando continuarán haciéndolo, pero los servidores de SSO no podrán cifrar credenciales nuevas.</span><span class="sxs-lookup"><span data-stu-id="d84dd-117">If the master secret server fails, all runtime operations already running will continue to run, but SSO servers will not be able to encrypt new credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d84dd-118">Sólo puede haber un servidor secreto principal en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="d84dd-118">There can be only one master secret server in your SSO system.</span></span> <span data-ttu-id="d84dd-119">Por tanto, se recomienda encarecidamente agrupar el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="d84dd-119">Therefore, it is strongly recommended you cluster the master secret server.</span></span> <span data-ttu-id="d84dd-120">Para obtener más información, consulte [cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md).</span><span class="sxs-lookup"><span data-stu-id="d84dd-120">For more information, see [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84dd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d84dd-121">See Also</span></span>  
 [<span data-ttu-id="d84dd-122">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="d84dd-122">Using SSO</span></span>](../core/using-sso.md)