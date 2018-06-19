---
title: Cómo usar el complemento de servidores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f520692-9606-41f5-98ed-5a4962bd1f09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12eb72323a6dcd1132f03febc9b4d9bd75316c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256564"
---
# <a name="how-to-use-the-servers-snap-in"></a>Cómo usar el complemento de servidores
Esta versión de Inicio de sesión único empresarial (SSO) incluye el complemento de servidores ENTSSO, que permite ver, supervisar y realizar determinadas acciones en el servidor ENTSSO mediante la interfaz de Windows.  
  
> [!NOTE]
>  Si el sistema tiene un servidor de seguridad y el nombre del servidor utiliza el formato FQDN, es posible que no pueda ponerse en contacto con el servidor. En su lugar, debe especificar el nombre NetBIOS o la dirección IP asociada.  
  
### <a name="to-use-the-entsso-servers-snap-in"></a>Para usar el complemento de servidores ENTSSO  
  
1.  Abra el Inicio de sesión único empresarial.  
  
2.  En el panel de ámbito, haga clic en el **servidores** nodo.  
  
     Aparecerá la siguiente información en el panel Resultados.  
  
    -   **Nombre**: nombre especificado.  
  
    -   **Estado**: estado del servicio ENTSSO (en línea, sin conexión, pendiente, iniciado, detenido, Inicio pendiente y detención pendiente).  
  
    -   **Fecha**: se obtuvo la información de fecha.  
  
    -   **Tiempo**: se obtuvo la información de tiempo.  
  
    -   **Servidor de SSO**: nombre completo del servidor.  
  
    -   **Cuenta de servicio**: cuenta de servicio ENTSSO.  
  
    -   **Base de datos de SSO**: base de datos de ENTSSO con la que se comunica este servidor.  
  
    -   **Servidor secreto**: indica si se está ejecutando el módulo servidor secreto.  
  
    -   **Sincronización de contraseñas**: indica si la sincronización de contraseñas está instalada.  
  
    -   **Equipo**: nombre NETBIOS del equipo.  
  
    -   **Recuentos de sucesos**: recuento de eventos de información/advertencia/errores. Restablecerlo iniciará el contador desde 0.  
  
    -   **Versión de SSO instalada**: número de versión de ENTSSO.exe. Además, indica si se trata de una versión de 32 bits (x86) o de 64 bits (x64).  
  
### <a name="to-start-or-stop-the-server-service"></a>Para iniciar o detener el servicio de servidor  
  
-   En lo servidores de complemento de ENTSSO, haga clic en el servidor y haga clic en **iniciar** o **detener**.  
  
### <a name="to-display-information-for-one-server"></a>Para mostrar la información de un servidor  
  
-   En el árbol del servidor, haga clic en el servidor.  
  
     Aparecerá la información en el panel de resultados.  
  
### <a name="to-add-a-server"></a>Procedimiento para agregar un servidor  
  
-   Haga clic en el panel de ámbito y, a continuación, haga clic en **Agregar servidor**.  
  
     El **Agregar servidor** aparece el cuadro de diálogo. Escriba el nombre del servidor que desea agregar o desplácese hasta su ubicación.  
  
> [!NOTE]
>  En determinados entornos de grupo de trabajo, haga clic en el **examinar** botón hará que cierre este cuadro de diálogo. En lugar de utilizar el **examinar** , simplemente escriba el nombre del servidor en el cuadro.  
  
### <a name="to-view-or-change-server-properties"></a>Para ver o cambiar las propiedades del servidor  
  
-   En el árbol de servidores, haga clic en el servidor y haga clic en **propiedades**.  
  
     El **propiedades del servidor** aparece el cuadro de diálogo. Puede ver o cambiar la información en las siguientes fichas:  
  
    -   **Niveles de auditoría**  
  
    -   **Base de datos SSO**  
  
    -   **Servicio SSO**  
  
    -   **Sincronización de contraseñas**  
  
    -   **Avanzadas**