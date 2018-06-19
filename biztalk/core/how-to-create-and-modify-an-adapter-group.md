---
title: Cómo crear y modificar un grupo de adaptadores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6865de8eb67d9fe1a6ca8d93b7d2e6527ae36364
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249228"
---
# <a name="how-to-create-and-modify-an-adapter-group"></a><span data-ttu-id="0d817-102">Cómo crear y modificar un grupo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="0d817-102">How to Create and Modify an Adapter Group</span></span>
<span data-ttu-id="0d817-103">Una de las nuevas características del inicio de sesión único (SSO) es la capacidad para crear y modificar grupos de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="0d817-103">One of the new features of Single Sign-On (SSO) is the ability to create and modify adapter groups.</span></span> <span data-ttu-id="0d817-104">Como indica su nombre, un grupo de adaptadores es una colección de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="0d817-104">As the name implies, an adapter group is a collection of adapters.</span></span> <span data-ttu-id="0d817-105">Puede utilizar grupos de adaptadores para organizar la configuración de seguridad y otras propiedades de los adaptadores.</span><span class="sxs-lookup"><span data-stu-id="0d817-105">You can use adapter groups to organize security settings and other properties for your adapters.</span></span>  
  
### <a name="to-create-and-modify-an-adapter-group"></a><span data-ttu-id="0d817-106">Para crear y modificar un grupo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="0d817-106">To create and modify an adapter group</span></span>  
  
1.  <span data-ttu-id="0d817-107">Cree el grupo de adaptadores con una llamada a la herramienta ssops.</span><span class="sxs-lookup"><span data-stu-id="0d817-107">Create the adapter group by using a call to the ssops tool.</span></span>  
  
     <span data-ttu-id="0d817-108">En el archivo XML asociado, debe establecer la marca de grupo como un grupo de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="0d817-108">In the associated XML file, you must set the group flag as an adapter group.</span></span>  
  
2.  <span data-ttu-id="0d817-109">Agregar uno o más adaptadores al grupo de adaptadores mediante `ISSOPSAdmin.AddAdapterToAdapterGroup`.</span><span class="sxs-lookup"><span data-stu-id="0d817-109">Add one or more adapters to the adapter group by using `ISSOPSAdmin.AddAdapterToAdapterGroup`.</span></span>  
  
     <span data-ttu-id="0d817-110">En este punto, el grupo de adaptadores está listo para trabajar como se desee.</span><span class="sxs-lookup"><span data-stu-id="0d817-110">At this point, your adapter group is ready to work as intended.</span></span> <span data-ttu-id="0d817-111">Si es necesario, puede ver la lista completa de los adaptadores asociados mediante `ISSOPSAdmin.GetAdaptersForAdapterGroup`.</span><span class="sxs-lookup"><span data-stu-id="0d817-111">If necessary, you can view the full list of associated adapters by using `ISSOPSAdmin.GetAdaptersForAdapterGroup`.</span></span>  
  
3.  <span data-ttu-id="0d817-112">Puede modificar la configuración de su grupo de adaptadores con `ISSOPSAdmin.SetAdapterProperties`.</span><span class="sxs-lookup"><span data-stu-id="0d817-112">You can modify the settings of your adapter group using `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
4.  <span data-ttu-id="0d817-113">Cuando haya terminado, puede quitar el adaptador de grupo de adaptadores con `ISSOPSAdmin.RemoveAdapterFromAdapterGroup`.</span><span class="sxs-lookup"><span data-stu-id="0d817-113">When you are finished, you can remove the adapter from the adapter group using `ISSOPSAdmin.RemoveAdapterFromAdapterGroup`.</span></span>  
  
5.  <span data-ttu-id="0d817-114">Por último, puede eliminar el grupo de adaptadores mediante `ISSOAdmin.DeleteApplication`.</span><span class="sxs-lookup"><span data-stu-id="0d817-114">Finally, you can delete the adapter group by using `ISSOAdmin.DeleteApplication`.</span></span>  
  
     <span data-ttu-id="0d817-115">Puede elegir en su lugar eliminar el grupo de adaptadores mediante el `-delete` comando de la herramienta ssops.</span><span class="sxs-lookup"><span data-stu-id="0d817-115">You may choose instead to delete the adapter group by using the `-delete` command of the ssops tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d817-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d817-116">See Also</span></span>  
 [<span data-ttu-id="0d817-117">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="0d817-117">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)