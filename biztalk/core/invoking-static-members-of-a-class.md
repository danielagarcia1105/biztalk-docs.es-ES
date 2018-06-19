---
title: Invocar miembros estáticos de una clase | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2128bf6cb71c773cd31be497765e39b0d7815b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262276"
---
# <a name="invoking-static-members-of-a-class"></a>Invocar miembros estáticos de una clase
De forma predeterminada, el motor de reglas necesita que imponga una instancia de una clase .NET para ejecutar una directiva que invoque un miembro estático de la clase .NET. Puede modificar este comportamiento si cambia el valor de la **StaticSupport** clave del registro bajo **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0** a uno de los valores en la tabla siguiente.  
  
|Valor del Registro StaticSupport|Comportamiento del motor de reglas|  
|----------------------------------|--------------------------|  
|0|Valor predeterminado. el motor de reglas sigue el modelo de BizTalk Server 2004, donde sólo se llama al método estático cuando se impone una instancia de la clase .NET.|  
|1|No se necesita una instancia del objeto. Se llama al método estático cuando se evalúa o ejecuta la regla.|  
|2|No se necesita una instancia del objeto. Se llama al método estático en el momento de traducción de la directiva si todos los parámetros son constantes. Esto supone una optimización del rendimiento porque se llama al método estático sólo una vez incluso aunque se use en varias reglas en condiciones. Tenga en cuenta que los métodos estáticos usados como acciones no se ejecutarán en el momento de traducción pero es posible que se ejecuten los métodos estáticos que se usen como parámetros.|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a>Agregar y cambiar la clave de Registro StaticSupport  
 Si no ve el **StaticSupport** clave del registro bajo **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, debería agregarla mediante los pasos siguientes.  
  
 **Para agregar la clave de registro StaticSupport**  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **RegEdit**y, a continuación, haga clic en **Aceptar**.  
  
2.  Expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Microsoft**, expanda **BusinessRules**y, a continuación, seleccione **3.0**.  
  
3.  En el panel derecho, haga clic en, seleccione **New**y, a continuación, haga clic en **valor DWORD**.  
  
4.  Para **nombre**, tipo **StaticSupport**.  
  
 Si el **StaticSupport** clave del registro ya existe y tiene que cambiar su valor, realice los pasos siguientes.  
  
> [!IMPORTANT]
>  Si BizTalk está instalado en un equipo de 64 bits, puede agregar **StaticSupport** clave del registro con cualquiera de las siguientes opciones:  
>   
>  -   Busque en HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0. Si existe esta clave, puede agregar **StaticSupport** aquí.  
> -   Otra opción consiste en colocar **StaticSupport** en el **BTNTsvc [64] exe. config** archivo, esta configuración reemplaza el contenido en el registro.  Además, también se puede argumentar que esta opción es preferible, ya que aísla el cambio del comportamiento predeterminado solo en BizTalk, mientras que la configuración del Registro se aplica a todo el sistema operativo.  
  
 **Para cambiar el valor de la clave de registro StaticSupport**  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **RegEdit**y, a continuación, haga clic en **Aceptar**.  
  
2.  Expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Microsoft**, expanda **BusinessRules**y, a continuación, expanda **3.0**.  
  
3.  Haga doble clic en el **StaticSupport** registro de clave, o haga clic en él y, a continuación, haga clic en **modificar**.