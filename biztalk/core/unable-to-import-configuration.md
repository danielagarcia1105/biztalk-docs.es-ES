---
title: No se puede importar la configuración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2887da50-4f74-4259-a7d6-c87bc9b9fc58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e565b466e4f9ce8af3745948952b4318a029ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286684"
---
# <a name="unable-to-import-configuration"></a>No se pudo importar la configuración
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se puede importar la configuración del archivo "{0}".|  
  
## <a name="explanation"></a>Explicación  
 Podrían haber varias razones para este error:  
  
-   Es posible que el archivo de configuración contega un carácter no válido en la codificación.  
  
-   Es posible que falte el elemento raíz.  
  
-   Es posible que los datos en el nivel de raíz no sean válidos.  
  
> [!NOTE]
>  Esta situación y la acción del usuario solo se aplican a los adaptadores de WCF-Custom y WCF-CustomIsolate.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para importar un archivo de configuración válido.  
  
#### <a name="to-import-a-valid-configuration-file"></a>Para importar un archivo de configuración válido  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **importación/exportación** ficha.  
  
9. Haga clic en **Importar**. Importe un archivo de configuración válido y completo.  
  
 También puede comprobar la validez del archivo de configuración, ábralo con el Editor de configuración de servicio **(Inicio > todos los programas > SDK de Windows)** (en este paso se asume que tiene instalado el SDK de Windows.) Abra **svcConfigEditor.exe** y compruebe todas las propiedades del archivo de configuración.