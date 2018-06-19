---
title: Configurar las propiedades de separador (X12) y reserva Charset | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477f4952-6a4e-4e98-a37f-f6e1fe7db3d3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633ea22c611eb0fab994fd62250b9cb9ff8a0f2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233844"
---
# <a name="configuring-fallback-charset-and-separator-properties-x12"></a>Configuración de propiedades de juegos de caracteres y separadores de reserva (X12)
En el acuerdo de reserva, puede especificar el juego de caracteres que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para validar las propiedades de entidad al crear el sobre para un mensaje X12 saliente. También puede especificar los separadores y terminadores que se usarán para los segmentos del intercambio.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a los intercambios HIPAA.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-character-set-and-separators"></a>Para configurar el juego de caracteres y los separadores  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.  
  
2.  En el **X12 configuración de reserva** cuadro de diálogo la **X12 páginas del acuerdo** , bajo la **configuración de intercambio** sección, haga clic en **juego de caracteres y separadores** .  
  
3.  Desde el **juego de caracteres que se utilizará** lista desplegable, seleccione el X12 juego de caracteres que se usa para validar las propiedades que especifique para el acuerdo.  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo usa esta configuración para validar los valores especificados para las propiedades de contrato relacionadas. La canalización de recepción o la de envío hará caso omiso de esta propiedad de juego de caracteres al realizar el procesamiento en tiempo de ejecución.  
  
4.  Para **elemento de datos**, especifique un único carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para separar elementos de datos compuestos que consten de dos o más elementos de datos simples y los elementos de datos simples que no forman parte de un elemento compuesto. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
5.  Para **separador de elementos de componente (ISA16)**, especifique un único carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para separar elementos de datos simples dentro de los elementos de datos compuestos. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
6.  Para **terminador de segmento**, especifique un único carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para indicar el final de un segmento EDI. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
7.  Para **sufijo**, seleccione el carácter que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utilizará con el identificador de segmento, puede ser **ninguno**, **CR** (retorno de carro), **LF** (avance de línea) o **CR LF** (retorno de carro/línea fuente). Si designa un sufijo, el elemento de datos de terminador de segmentos puede estar vacío. Si el terminador de segmentos se deja vacío, debe designar un sufijo. La combinación de terminador de segmento y sufijo puede ser cualquiera de las siguientes:  
  
    -   Terminador de segmento  
  
    -   Terminador de segmento + retorno de carro  
  
    -   Terminador de segmento + retorno de carro/avance de línea  
  
    -   Retorno de carro  
  
    -   Avance de línea  
  
    -   Retorno de carro/avance de línea  
  
8.  Si los datos de carga contienen caracteres que también se usan como datos, segmentos o separadores de componentes, consulte **reemplazar separadores de carga con** y especificar un carácter de reemplazo. Al generar el mensaje X12 de salida, todas las instancias de caracteres de separador en los datos de carga se sustituirán por el carácter especificado. Seleccione **Char** para un elemento de datos de caracteres o **hexadecimal** para un elemento de datos hexadecimales. El carácter que escriba cambiará automáticamente cuando se cambia el formato de **Char** a **hexadecimal** o viceversa.  
  
9. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de X12 propiedades de acuerdo de reserva para el procesamiento de intercambio](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)