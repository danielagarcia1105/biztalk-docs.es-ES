---
title: Cómo configurar un adaptador de sincronización de contraseña | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0effdc9b-4aee-4674-90c5-03dfd7cc4cd6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f0be0146e905ef291942bd30adc111eff89e989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247356"
---
# <a name="how-to-configure-a-password-sync-adapter"></a><span data-ttu-id="7164d-102">Cómo configurar un adaptador de sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="7164d-102">How to Configure a Password Sync Adapter</span></span>
<span data-ttu-id="7164d-103">Cuando haya terminado de crear el adaptador de sincronización de contraseñas, debe cargarlo en un sistema.</span><span class="sxs-lookup"><span data-stu-id="7164d-103">After you have finished creating your password sync adapter, you must load your adapter on to a system.</span></span> <span data-ttu-id="7164d-104">Asimismo, debe informar al inicio de sesión único empresarial (ENTSSO) y al almacén de configuración de que la aplicación es un adaptador de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="7164d-104">Additionally, you must inform Enterprise Single Sign-On (ENTSSO) and the configuration store that your application is a password sync adapter.</span></span> <span data-ttu-id="7164d-105">Debe registrar con el almacén de configuración por motivos de seguridad: el adaptador solicitará actualizaciones de contraseñas y otras credenciales.</span><span class="sxs-lookup"><span data-stu-id="7164d-105">You must register with the configuration store for security purposes: your adapter will request updates to passwords and other credentials.</span></span> <span data-ttu-id="7164d-106">Por lo tanto, ENTSSO debe saber que un determinado adaptador tiene autorización para pedir estos permisos.</span><span class="sxs-lookup"><span data-stu-id="7164d-106">Therefore, ENTSSO must know that a given adapter is allowed to ask for such permissions.</span></span>  
  
### <a name="to-configure-a-password-sync-adapter"></a><span data-ttu-id="7164d-107">Para configurar un adaptador de sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7164d-107">To configure a password sync adapter</span></span>  
  
1.  <span data-ttu-id="7164d-108">Cree el adaptador con el almacén de configuración mediante la herramienta ssops.</span><span class="sxs-lookup"><span data-stu-id="7164d-108">Create your adapter with the configuration store using the ssops tool.</span></span>  
  
     <span data-ttu-id="7164d-109">Al utilizar ssops, cargará un archivo de configuración XML en la base de datos de configuración que describe la aplicación en el inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="7164d-109">Using ssops, you load an XML configuration file into the configuration database that describes your application to Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="7164d-110">Después de crear el adaptador con la base de datos de configuración, puede modificar la información del adaptador con `ISSOPSAdmin.SetAdapterProperties`.</span><span class="sxs-lookup"><span data-stu-id="7164d-110">After you create the adapter with the config database, you can modify the adapter information with `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
     <span data-ttu-id="7164d-111">Aunque los dos métodos son similares, `SetAdapterProperties` envía un mensaje al adaptador cuando cambia la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="7164d-111">While the two methods are similar, `SetAdapterProperties` sends a message to the adapter when the configuration information changes.</span></span>  
  
3.  <span data-ttu-id="7164d-112">Para eliminar un adaptador, use ISSOAdmin.DeleteApplication.</span><span class="sxs-lookup"><span data-stu-id="7164d-112">To delete an adapter, use ISSOAdmin.DeleteApplication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7164d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7164d-113">See Also</span></span>  
 [<span data-ttu-id="7164d-114">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="7164d-114">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)