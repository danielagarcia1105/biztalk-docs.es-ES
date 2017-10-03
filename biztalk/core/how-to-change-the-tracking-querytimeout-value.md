---
title: "Cómo cambiar el valor de QueryTimeout de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [HAT], time-out limits
- HAT, time-out limits
ms.assetid: abc26f37-6537-42fa-81ff-bc8b758b4e10
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca9f61466323e0b154bdeb0499cc5cee6e4ef10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-tracking-querytimeout-value"></a>Cambio del valor QueryTimeout de seguimiento
De forma predeterminada, el seguimiento de instancias de mensajes y servicios agotará el tiempo de espera si una consulta se ejecuta durante más de 60 segundos. Es posible cambiar el valor de tiempo de espera en el Registro para permitir que las consultas se ejecuten durante más de 60 segundos.  
  
> [!CAUTION]
>  Una modificación incorrecta del Registro puede provocar daños graves en el sistema. Antes de efectuar cambios en el Registro, debe realizar una copia de seguridad de los datos importantes del equipo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.  
  
### <a name="to-change-the-query-timeout-value"></a>Para cambiar el valor de tiempo de espera de consulta  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el Editor del Registro, busque y haga clic en la siguiente subclave:  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3. 0**  
  
3.  Si existe una subclave Tracking, vaya al paso 6.  
  
4.  Para crear una subclave Tracking, en la **editar** menú, elija **New**y, a continuación, haga clic en **clave**.  
  
5.  Tipo de **seguimiento**, y, a continuación, presione ENTRAR.  
  
6.  Busque la siguiente subclave y haga clic en ella:  
  
     **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\Tracking**  
  
7.  En el **editar** menú, elija **New**y, a continuación, haga clic en **valor DWORD**.  
  
8.  Tipo de **ConnectionTimeout**, y, a continuación, presione ENTRAR.  
  
9. Haga clic en **ConnectionTimeout**y, a continuación, haga clic en **modificar**.  
  
10. En el **Editar valor DWORD** cuadro de diálogo, haga clic en **Decimal**.  
  
11. En el **datos del valor** cuadro, escriba el valor en segundos que se desea establecer para el valor de tiempo de espera de consulta y, a continuación, haga clic en **Aceptar**.  
  
12. En el menú **Archivo** , haga clic en **Salir**.  
  
    > [!NOTE]
    >  Es posible que sea necesario cerrar y luego volver a abrir la consola de administración de BizTalk Server para que el nuevo valor de tiempo de espera surta efecto.  
  
## <a name="see-also"></a>Vea también  
 [Ver los datos históricos y de seguimiento](../core/viewing-historical-and-tracked-data.md)