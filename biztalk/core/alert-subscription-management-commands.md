---
title: "Comandos de administración de suscripciones de alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cd6ad27-6217-466a-b616-4b26fb31b0af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914d5cd9ac19e160c1f26df3f762f81fb89345d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="alert-subscription-management-commands"></a>Comandos de administración de suscripciones de alertas
Los comandos de administración de suscripciones de la utilidad de administración de BAM permiten trabajar con suscripciones de alertas.  
  
-   get-subscription: Obtiene una lista de suscriptores a una alerta.  
  
-   Agregar suscripción: agrega un suscriptor a una alerta.  
  
-   Remove-subscription: quita un suscriptor de una alerta.  
  
> [!NOTE]
>  Puede habilitar el seguimiento de cualquier comando de la utilidad BM incluyendo el **-Trace: en &#124; desactivar** modificador de parámetro. Al utilizar el conmutador Trace, se invalidan las opciones de seguimiento del archivo de configuración. El conmutador puede utilizarse junto con cualquier comando normal de BM.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="get-subscription-command"></a>get-subscription (comando)  
 **Uso**  
  
 **bm.exe get-subscriptions-View:\<nombre de vista >-alerta:\<nombre de la alerta > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista >|Nombre de la vista en la que se va a especificar la alerta.|  
|Alerta:\<nombre de la alerta >|Nombre de la alerta desde la que se va a obtener la suscripción.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Enumera todos los suscriptores de la alerta especificada.  
  
 **Ejemplos**  
  
```  
bm.exe get-subscriptions -View:SalesManagerView -Alert:SalesTooLow  
bm.exe get-subscriptions -View:Shipments -Alert:SlowShipment -Server:Ship1  
```  
  
## <a name="add-subscription-command"></a>add-subscription (comando)  
 **Uso**  
  
 **suscripción de bm.exe-vista:\<nombre de la vista >-Alert:\<nombre de la alerta > - AccountName:\<nombre de cuenta >-tipo: [archivo de &#124; Email] [-correo electrónico:\<dirección de correo electrónico >] [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista >|Nombre de la vista en la que se especifica la alerta.|  
|Alerta:\<nombre de la alerta >|Nombre de la alerta a la que se va a suscribir.|  
|AccountName:\<nombre de cuenta >|Cuenta, con formato dominio\usuario, que se va a suscribir a la alerta.|  
|Tipo: [Archivo de &#124; Correo electrónico]|Tipo de entrega de la alerta. Si especifica un tipo de entrega de correo electrónico, debe incluir el parámetro de correo electrónico en la línea de comandos.|  
|Correo electrónico:\<dirección de correo electrónico >|Opcional: La dirección de correo electrónico a la que se va a entregar la notificación de alerta.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Agrega una suscripción para la cuenta especificada a la alerta especificada.  
  
 **Ejemplos**  
  
```  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:File  
bm.exe add-subscription -View:v1 -Alert:a2 -AccountName:domain\user -Type:Email -Email:useremail@domain.com  
```  
  
## <a name="remove-subscription-command"></a>remove-subscription (comando)  
 **Uso**  
  
 **bm.exe remove-subscription-View:\<nombre de la vista >-alerta:\<nombre de la alerta > - AccountName:\<nombre de cuenta > [-Server:\<servidor >] [-base de datos:\<base de datos >]**  
  
 **Parámetros**  
  
|Parámetro|Description|  
|---------------|-----------------|  
|Vista:\<nombre de vista >|Nombre de la vista en la que se especifica la alerta.|  
|Alerta:\<nombre de la alerta >|Nombre de la alerta.|  
|AccountName:\<nombre de cuenta >|Cuenta, con formato dominio\usuario, que se va a quitar de la alerta.|  
|Servidor:\<server >|Opcional: El nombre del servidor en el que reside la vista. El servidor debe estar en el mismo dominio que el equipo desde el que se ejecuta bm.exe. Si no se especifica el nombre de servidor, bm.exe utiliza el nombre predeterminado de localhost.|  
|Base de datos:\<base de datos >|Opcional: El nombre de la base de datos en el que reside la vista. Si no se especifica el nombre, bm.exe usa el nombre predeterminado BamPrimaryImport.|  
  
 Quita la suscripción de la cuenta especificada de la alerta especificada. Se quitan todas las suscripciones para la cuenta especificada.  
  
 **Ejemplos**  
  
```  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:domain\user  
bm.exe remove-subscription -View:v1 -Alert:a2 -AccountName:user -Server:s1  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)