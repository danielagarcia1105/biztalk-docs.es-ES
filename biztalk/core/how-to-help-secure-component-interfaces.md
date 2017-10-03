---
title: "Cómo ayudar a componente seguro Interfaces | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, helping to secure
- security, component interfaces
ms.assetid: 03b2af44-78e7-4fdc-bfa3-7697b2a60986
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54136aaeae9578ae4e438c5bd8b95b902d618f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-help-secure-component-interfaces"></a><span data-ttu-id="230a7-102">Cómo proteger las interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="230a7-102">How to Help Secure Component Interfaces</span></span>
<span data-ttu-id="230a7-103">Antes de que pueda probar una interfaz de componente, debe establecer la seguridad para ésta.</span><span class="sxs-lookup"><span data-stu-id="230a7-103">Before you can start testing a component interface, you must set up security for it.</span></span> <span data-ttu-id="230a7-104">El siguiente procedimiento describe cómo configurar la seguridad de interfaz de componentes para la versión 8.4 de PeopleSoft pero puede utilizar le procedimiento para la versión 8.1.</span><span class="sxs-lookup"><span data-stu-id="230a7-104">The following procedure describes how to configure component interface security for PeopleSoft Version 8.4, but you can use the procedure for Version 8.1.</span></span>  
  
### <a name="to-configure-interface-security"></a><span data-ttu-id="230a7-105">Para configurar la seguridad de interfaz</span><span class="sxs-lookup"><span data-stu-id="230a7-105">To configure interface security</span></span>  
  
1.  <span data-ttu-id="230a7-106">Expanda **PeopleTools**, expanda **seguridad**, expanda **perfiles de usuario**y, a continuación, expanda **permisos y Roles**.</span><span class="sxs-lookup"><span data-stu-id="230a7-106">Expand **PeopleTools**, expand **Security**, expand **User Profiles**, and then expand **Permissions & Roles**.</span></span>  
  
     ![](../core/media/psadapter-47-ps-configsecurity1.gif "PSAdapter_47_PS_ConfigSecurity1")  
  
2.  <span data-ttu-id="230a7-107">Haga clic en **las listas de permisos**.</span><span class="sxs-lookup"><span data-stu-id="230a7-107">Click **Permission Lists**.</span></span>  
  
3.  <span data-ttu-id="230a7-108">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="230a7-108">Click **Search**.</span></span>  
  
     ![](../core/media/psadapter-48-ps-configsecurity2.gif "PSAdapter_48_PS_ConfigSecurity2")  
  
4.  <span data-ttu-id="230a7-109">En el **búsqueda de listas de permiso** panel, seleccione la lista de los permisos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="230a7-109">In the **Permission Lists Search** pane, select the relevant permission list.</span></span>  
  
     <span data-ttu-id="230a7-110">Aparecerá la siguiente ventana.</span><span class="sxs-lookup"><span data-stu-id="230a7-110">The following window appears.</span></span>  
  
     ![](../core/media/psadapter-49-ps-configsecurity3.gif "PSAdapter_49_PS_ConfigSecurity3")  
  
5.  <span data-ttu-id="230a7-111">Haga clic en la flecha derecha junto a la **tiempos de inicio de sesión** pestaña para visualizar más fichas.</span><span class="sxs-lookup"><span data-stu-id="230a7-111">Click the right arrow next to the **Sign-on Times** tab to display more tabs.</span></span>  
  
     ![](../core/media/psadapter-50-ps-configsecurity4.gif "PSAdapter_50_PS_ConfigSecurity4")  
  
6.  <span data-ttu-id="230a7-112">Haga clic en el **Interfaces de componentes** ficha.</span><span class="sxs-lookup"><span data-stu-id="230a7-112">Click the **Component Interfaces** tab.</span></span>  
  
7.  <span data-ttu-id="230a7-113">Haga clic en el + (más) de inicio de sesión para agregar una nueva fila a la **Interfaces de componentes** lista.</span><span class="sxs-lookup"><span data-stu-id="230a7-113">Click the + (plus) sign to add a new row to the **Component Interfaces** list.</span></span>  
  
     <span data-ttu-id="230a7-114">Aparecerá un campo en el que puede escribir el nombre de la interfaz de componente.</span><span class="sxs-lookup"><span data-stu-id="230a7-114">A field appears in which you can type the component interface name.</span></span>  
  
     ![](../core/media/psadapter-51-ps-configsecurity5.gif "PSAdapter_51_PS_ConfigSecurity5")  
  
8.  <span data-ttu-id="230a7-115">Escriba el nombre de la interfaz de componente y, a continuación, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="230a7-115">Type the component interface name, and then click **Edit**.</span></span>  
  
     <span data-ttu-id="230a7-116">Este ejemplo usa la interfaz de componente AR_ITEM_AGENT.</span><span class="sxs-lookup"><span data-stu-id="230a7-116">This example uses component interface AR_ITEM_AGENT.</span></span>  
  
     ![](../core/media/psadapter-52-ps-configsecurity6.gif "PSAdapter_52_PS_ConfigSecurity6")  
  
9. <span data-ttu-id="230a7-117">En la lista, seleccione el nivel de acceso deseado para cada método y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="230a7-117">In the list, select the desired access level for each method, and then click **OK**.</span></span>  
  
     <span data-ttu-id="230a7-118">Aparecerá la siguiente ventana.</span><span class="sxs-lookup"><span data-stu-id="230a7-118">The following window appears.</span></span>  
  
     ![](../core/media/psadapter-53-ps-configsecurity7.gif "PSAdapter_53_PS_ConfigSecurity7")  
  
10. <span data-ttu-id="230a7-119">Desplácese hacia abajo en el panel derecho y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="230a7-119">Scroll down in the right pane, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="230a7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="230a7-120">See Also</span></span>  
 <span data-ttu-id="230a7-121">[Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="230a7-121">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="230a7-122">Apéndice C: usar Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="230a7-122">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)