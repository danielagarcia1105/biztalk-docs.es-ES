--title: "configurar MSDTC en el cliente SQL Server y el adaptador | Microsoft Docs"ms.custom:" "ms.date:" 08/06/2017"ms.prod:"biztalk server"ms.reviewer:" "

MS.Suite: "" ms.tgt_pltfrm: "" ms.topic: "article" ms.assetid: 2c87f455-a8c4-4169-bf18-695926136df1 caps.latest.revision: 14 author: "MandiOhlinger" ms.author: "mandia" manager: "anneta"
---
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a>Configurar MSDTC en el cliente de SQL Server y el adaptador
Las operaciones realizan en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el modelo de servicio WCF o el modelo de canal WCF) se pueden realizar en un ámbito de transacción. Si el programa cliente tiene más de un recurso transaccional como parte de la misma transacción, la transacción obtiene elevada a una transacción MSDTC. Para habilitar el adaptador realizar operaciones dentro del ámbito de una transacción MSDTC, debe configurar MSDTC tanto en el equipo que ejecuta el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y SQL Server. Además, debe agregar MSDTC a la lista de excepciones de Firewall de Windows. Esta sección proporciona información acerca de cómo realizar estas tareas en los equipos que ejecutan el cliente del adaptador y SQL Server.  
  
> [!NOTE]
>  Realizar operaciones en SQL Server mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] siempre implica dos recursos, el adaptador que se conecta a SQL Server y el cuadro de mensaje de BizTalk que se encuentran en SQL Server. Por lo tanto, todas las operaciones realizan mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se realizan dentro del ámbito de una transacción MSDTC. Por lo tanto, para usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre debe habilitar MSDTC.  
> 
> [!NOTE]
>  Para las operaciones donde el cliente del adaptador no escribe ningún dato en la base de datos de SQL Server, como una operación Select, no podría la sobrecarga adicional de llevar a cabo las operaciones dentro de una transacción. En tales casos, puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para realizar las operaciones sin un contexto transaccional estableciendo el **UseAmbientTransaction** enlazar la propiedad a **false**. Para obtener más información acerca de la propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). En tales casos, no es necesario configurar MSDTC también.  
  
## <a name="configure-msdtc"></a>Configurar MSDTC  
  
1. Abra **servicios de componentes**.  

   O bien, en **administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **servicios de componentes**.  
  
2. Expanda **servicios de componentes**, expanda **equipos**, expanda **Mi PC**, expanda **Coordinador de transacciones distribuidas**, Haga clic en **DTC Local**y seleccione **propiedades**.  
  
3. Seleccione la pestaña **Seguridad** . En esta pestaña, seleccione todos los elementos siguientes: 

   - **Acceso a DTC desde la red**
   - **Permitir a clientes remotos** 
   - **Permitir entrantes** 
   - **Permitir salientes** 
   - **No se requiere autenticación**
  
4. Seleccione **Aceptar** para guardar los cambios.  
  
5. Si se le pida que reinicie el servicio MSDTC, seleccione **Sí**. Después de reinicia el servicio MSDTC, cierre las propiedades y los servicios de componentes de MMC. 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a>Agregar MSDTC a la lista de excepciones de Firewall de Windows  

> [!TIP] 
>  Coordinador de transacción distribuida de Microsoft (MSDTC) puede que ya se permitidas en el firewall. Si es así, aparece como una regla de entrada. Si no aparece, use esta sección para permitir MSDTC. 

1.  Abra **Windows Firewall**y seleccione **configuración avanzada** a la izquierda.  

    O bien, en **administrador del servidor**, seleccione **herramientas**y, a continuación, seleccione **Firewall de Windows con seguridad avanzada**.  
  
2.  Haga clic en **reglas de entrada**y seleccione **nueva regla**.  
  
3.  En el asistente: 

    1. Seleccione **programa**y seleccione **siguiente**. 
    2. Establecer el **ruta del programa** a `%SystemRoot%\system32\msdtc.exe`y seleccione **siguiente**.  
    3. **Permitir la conexión**y seleccione **siguiente**.
    4. Seleccione **dominio**y seleccione **siguiente**.
    5. Escriba cualquier nombre, como `MSDTC for Oracle EBS`y seleccione **finalizar**.
  
5.  Complete el asistente y cierre Firewall de Windows. 
  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
