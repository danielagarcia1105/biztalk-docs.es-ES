---
title: 'De sesión único: Evento 10854 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8faed9d-5c7e-4b99-bcd9-ea5f670d5e72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f89ef2727933e72de1e9d759bd91dc507a0954
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994410"
---
# <a name="single-sign-on-event-10854"></a>De sesión único: Evento 10854
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10854                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |               ENTSSO_E_INVALID_STRING_FORMAT               |
|  Texto del mensaje   |     Formato de cadena incorrecto para esta función.      |
  
## <a name="explanation"></a>Explicación  
 Formato de cadena incorrecto para esta función.  
  
## <a name="user-action"></a>Acción del usuario  
 A continuación se describe el formato adecuado para cadenas de contraseña:  
  
 Propiedad de tipo VT_BSTR  
  
 El delimitador es / (barra diagonal)  
  
 dc = caso predeterminado (ninguna operación - no hacer nada)  
  
 Ejemplo: dc /  
  
 (ningún cambio: de 'Cat' a 'Cat')  
  
 uc = mayúsculas  
  
 Ejemplo: comunicaciones unificadas /  
  
 (cambiar contraseña a mayúsculas: de 'Cat' a 'CAT')  
  
 lc = minúsculas  
  
 Ejemplo: lc /  
  
 (cambiar contraseña a minúsculas: de 'Cat' a 'cat')  
  
 rc = quitar caracteres - seguido de recuento seguido de caracteres  
  
 Ejemplo: rc/2 / #@/  
  
 (quite los caracteres '#' y ' @' de la contraseña: 'C@t#' a 'Ct')  
  
 sc = caracteres sustitutos - seguido de recuento seguido de caracteres por reemplazar seguido de caracteres sustitutos  
  
 Ejemplo: sc/3/abc/def /  
  
 (quitar los caracteres 'a', 'b' y 'c' de la contraseña y reemplazarlos por 'd', 'e' y 'f', respectivamente)  
  
 (de 'Cat' a 'Cdt')  
  
 ps = completar desde el principio - seguido por recuento (longitud mín. de contraseña) seguido por un solo carácter controlador  
  
 Ejemplo: ps/8 / #/  
  
 (si la contraseña no tiene 8 caracteres como mínimo, completar desde el principio con el carácter '#' hasta que haya 8 caracteres en total)  
  
 (de 'Cat' a '#####Cat')  
  
 pe = completar desde el final - seguido por recuento (longitud mín. de contraseña) seguido por un solo carácter controlador  
  
 Ejemplo: pe/10 / $/  
  
 (si la contraseña no tiene 10 caracteres como mínimo, completar desde el final con el carácter '$' hasta que haya 10 caracteres en total)  
  
 (de 'Cat' a 'Cat$$$$$$$')  
  
 tr = truncar - límite de longitud de cadena - seguido de recuento  
  
 Ejemplo: tr/11 /  
  
 (de 'Cat123456789' a 'Cat12345678');  
  
 Los token se procesan en su orden en la cadena.  
  
 Ejemplo:  
  
 uc/rc/1/&/sc/2/#$/--/ps/8/&/tr/32/