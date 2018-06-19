---
title: Cómo cambiar el valor de QueryTimeout de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca9f61466323e0b154bdeb0499cc5cee6e4ef10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247476"
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a><span data-ttu-id="dc06b-102">Cambio del valor QueryTimeout de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dc06b-102">How to Change the Tracking QueryTimeout Value</span></span>
<span data-ttu-id="dc06b-103">De forma predeterminada, el seguimiento de instancias de mensajes y servicios agotará el tiempo de espera si una consulta se ejecuta durante más de 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="dc06b-103">By default, message and service instance tracking will time out if a query runs longer than 60 seconds.</span></span> <span data-ttu-id="dc06b-104">Es posible cambiar el valor de tiempo de espera en el Registro para permitir que las consultas se ejecuten durante más de 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="dc06b-104">You can change the timeout value in the registry to enable queries to run longer than 60 seconds.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="dc06b-105">Una modificación incorrecta del Registro puede provocar daños graves en el sistema.</span><span class="sxs-lookup"><span data-stu-id="dc06b-105">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="dc06b-106">Antes de efectuar cambios en el Registro, debe realizar una copia de seguridad de los datos importantes del equipo.</span><span class="sxs-lookup"><span data-stu-id="dc06b-106">Before making changes to the registry, you should back up any valued data on the computer.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dc06b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dc06b-107">Prerequisites</span></span>  
 <span data-ttu-id="dc06b-108">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="dc06b-108">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-change-the-query-timeout-value"></a><span data-ttu-id="dc06b-109">Para cambiar el valor de tiempo de espera de consulta</span><span class="sxs-lookup"><span data-stu-id="dc06b-109">To change the query timeout value</span></span>  
  
1.  <span data-ttu-id="dc06b-110">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dc06b-110">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="dc06b-111">En el Editor del Registro, busque y haga clic en la siguiente subclave:</span><span class="sxs-lookup"><span data-stu-id="dc06b-111">In Registry Editor, locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="dc06b-112">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3. 0**</span><span class="sxs-lookup"><span data-stu-id="dc06b-112">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0**</span></span>  
  
3.  <span data-ttu-id="dc06b-113">Si existe una subclave Tracking, vaya al paso 6.</span><span class="sxs-lookup"><span data-stu-id="dc06b-113">If there is a Tracking subkey, go to step 6.</span></span>  
  
4.  <span data-ttu-id="dc06b-114">Para crear una subclave Tracking, en la **editar** menú, elija **New**y, a continuación, haga clic en **clave**.</span><span class="sxs-lookup"><span data-stu-id="dc06b-114">To create a Tracking subkey, on the **Edit** menu, point to **New**, and then click **Key**.</span></span>  
  
5.  <span data-ttu-id="dc06b-115">Tipo de **seguimiento**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dc06b-115">Type **Tracking**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="dc06b-116">Busque la siguiente subclave y haga clic en ella:</span><span class="sxs-lookup"><span data-stu-id="dc06b-116">Locate and then click the following subkey:</span></span>  
  
     <span data-ttu-id="dc06b-117">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**</span><span class="sxs-lookup"><span data-stu-id="dc06b-117">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**</span></span>  
  
7.  <span data-ttu-id="dc06b-118">En el **editar** menú, elija **New**y, a continuación, haga clic en **valor DWORD**.</span><span class="sxs-lookup"><span data-stu-id="dc06b-118">On the **Edit** menu, point to **New**, and then click **DWORD Value**.</span></span>  
  
8.  <span data-ttu-id="dc06b-119">Tipo de **ConnectionTimeout**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dc06b-119">Type **ConnectionTimeout**, and then press ENTER.</span></span>  
  
9. <span data-ttu-id="dc06b-120">Haga clic en **ConnectionTimeout**y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="dc06b-120">Right-click **ConnectionTimeout**, and then click **Modify**.</span></span>  
  
10. <span data-ttu-id="dc06b-121">En el **Editar valor DWORD** cuadro de diálogo, haga clic en **Decimal**.</span><span class="sxs-lookup"><span data-stu-id="dc06b-121">In the **Edit DWORD Value** dialog box, click **Decimal**.</span></span>  
  
11. <span data-ttu-id="dc06b-122">En el **datos del valor** cuadro, escriba el valor en segundos que se desea establecer para el valor de tiempo de espera de consulta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dc06b-122">In the **Value data** box, type the value in seconds that you want to set for the query timeout value, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="dc06b-123">En el menú **Archivo** , haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="dc06b-123">On the **File** menu, click **Exit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc06b-124">Es posible que sea necesario cerrar y luego volver a abrir la consola de administración de BizTalk Server para que el nuevo valor de tiempo de espera surta efecto.</span><span class="sxs-lookup"><span data-stu-id="dc06b-124">You may need to close and then reopen the BizTalk Server Administration Console in order for the new timeout value to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc06b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc06b-125">See Also</span></span>  
 [<span data-ttu-id="dc06b-126">Ver los datos históricos y de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dc06b-126">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)