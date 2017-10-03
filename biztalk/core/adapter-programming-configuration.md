---
title: "Configuración de programación del adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e5fef6c-6928-42e7-9a1f-42b5bd769937
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e908b3ac79970b917e1e7964868b3b9d5bd852d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-programming-configuration"></a><span data-ttu-id="64570-102">Configuración de programación del adaptador</span><span class="sxs-lookup"><span data-stu-id="64570-102">Adapter Programming Configuration</span></span>
<span data-ttu-id="64570-103">Todos los tipos de adaptador de sincronización de contraseñas poseen diferentes requisitos de configuración en función de los sistemas ajenos a Windows para los que diseñe el adaptador.</span><span class="sxs-lookup"><span data-stu-id="64570-103">Every type of password sync adapter has different configuration requirements, depending on what non-Windows system you design the adapter for.</span></span> <span data-ttu-id="64570-104">Al igual que en el caso de las aplicaciones afiliadas, puede utilizar el almacenamiento de configuración de inicio de sesión único (SSO) empresarial para almacenar propiedades de configuración de manera central y más segura.</span><span class="sxs-lookup"><span data-stu-id="64570-104">Like affiliate applications, you can use the Enterprise Single Sign-On configuration store to store configuration properties centrally and more securely.</span></span>  
  
 <span data-ttu-id="64570-105">Como ocurre con el resto de aplicaciones de almacenamiento de configuración, un administrador puede utilizar la interfaz de usuario de administración de inicio de sesión único (SSO) empresarial para ubicar y leer un archivo XML que describe las propiedades de configuración para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="64570-105">As with other configuration store applications, an administrator can use the Enterprise Single Sign-On management user interface to locate and read an XML file that describes the configuration properties for your adapter.</span></span> <span data-ttu-id="64570-106">Las herramientas de administración utilizan el archivo XML para presentar una página de propiedades que reúna los valores de propiedades necesarios para el adaptador específico.</span><span class="sxs-lookup"><span data-stu-id="64570-106">The management tools use the XML file to render a property page to gather the required property values, for the specified adapter.</span></span> <span data-ttu-id="64570-107">También puede usar ISSOConfigStore para cargar y leer combinaciones de nombre/valor XML desde y hacia el almacén de configuración, o puede utilizar la herramienta SSOPS.</span><span class="sxs-lookup"><span data-stu-id="64570-107">You can also use ISSOConfigStore to load and read XML name/value combinations to and from the configuration store, or you can use the SSOPS tool.</span></span>  
  
 <span data-ttu-id="64570-108">También puede utilizar las herramientas de administración de inicio de sesión único (SSO) empresarial para habilitar o deshabilitar un adaptador.</span><span class="sxs-lookup"><span data-stu-id="64570-108">You can also use the Enterprise Single Sign-On administration tools to enable and disable an adapter.</span></span> <span data-ttu-id="64570-109">En el momento de la creación, el adaptador está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="64570-109">On initial creation, an adapter is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64570-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="64570-110">See Also</span></span>  
 [<span data-ttu-id="64570-111">Adaptadores de sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="64570-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)