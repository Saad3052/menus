**For Option menu main**

        Toolbar toolbar = findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);
**For Option menu main end**
**For Option menu**

    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {
        int itemid = item.getItemId();
        if(itemid == R.id.menuprofile)
        {
            Toast.makeText(getBaseContext(),"Profile Clicked",Toast.LENGTH_SHORT).show();
        }
        if(itemid == R.id.devices)
        {
            Toast.makeText(getBaseContext(),"Devices Clicked",Toast.LENGTH_SHORT).show();
        }if(itemid == R.id.menusetting)
        {
            Toast.makeText(getBaseContext(),"Setting Clicked",Toast.LENGTH_SHORT).show();
        }if(itemid == R.id.menuexit)
        {
            Toast.makeText(getBaseContext(),"Exit Clicked",Toast.LENGTH_SHORT).show();
        }if(itemid == R.id.logout)
        {
            Toast.makeText(getBaseContext(),"Logout Clicked",Toast.LENGTH_SHORT).show();
        }
        return super.onOptionsItemSelected(item);
    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        MenuInflater menuInflater = new MenuInflater(this);
        menuInflater.inflate(R.menu.option_menu,menu);

        return true;
    }
**For Option menu end**

**Option menu XML**

<?xml version="1.0" encoding="utf-8"?>

<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"

    xmlns:app="http://schemas.android.com/apk/res-auto"
    
    xmlns:tools="http://schemas.android.com/tools"
    
    android:id="@+id/main"
    
    android:layout_width="match_parent"
    
    android:layout_height="match_parent"
    
    tools:context=".MainActivity">
    
<androidx.appcompat.widget.Toolbar

        android:id="@+id/toolbar"
        
        android:layout_width="0dp"
        
        android:layout_height="wrap_content"
        
        android:background="#4161ff"
        
        app:layout_constraintEnd_toEndOf="parent"
        
        app:layout_constraintStart_toStartOf="parent"
        
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>


create new file option_menu.xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/menuprofile"
        android:title="profile"/>
    <item
        android:id="@+id/menusetting"
        android:title="setting"/>
    <item
        android:id="@+id/menumoreopt"
        android:title="More Option">
        <menu>
            <item
                android:id="@+id/devices"
                android:title="Devices"/>
            <item
                android:id="@+id/logout"
                android:title="Logout"/>
        </menu>
    </item>
    <item
        android:id="@+id/menuexit"
        android:title="Exit"/>
</menu>
**Option menu XML end**
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
**For context menu main**

        TextView textView = findViewById(R.id.context_textview);
        registerForContextMenu(textView);
**For context menu main end**
**For context menu**

    @Override
    public boolean onContextItemSelected(@NonNull MenuItem item) {
        int itema = item.getItemId();
        if(itema==R.id.cut)
        {
            Toast.makeText(getBaseContext(),"Cut clicked",Toast.LENGTH_SHORT).show();
        }
        if(itema==R.id.copy)
        {
            Toast.makeText(getBaseContext(),"Copy clicked",Toast.LENGTH_SHORT).show();
        }
        if(itema==R.id.paste)
        {
            Toast.makeText(getBaseContext(),"Paste clicked",Toast.LENGTH_SHORT).show();
        }
        return super.onContextItemSelected(item);
    }

    @Override
    public void onCreateContextMenu(ContextMenu menu, View v, ContextMenu.ContextMenuInfo menuInfo) {
        MenuInflater menuInflater = new MenuInflater(this);
        menuInflater.inflate(R.menu.context_menu,menu);
    }

**For context menu end**
**For context menu XML**
 <TextView
        android:id="@+id/context_textview"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click for context Menu"
        android:textIsSelectable="true"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/toolbar" />

Create new file:
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/cut"
        android:title="cut"/>
    <item
        android:id="@+id/copy"
        android:title="copy"/>
    <item
    android:id="@+id/paste"
    android:title="paste"/>
</menu>
**context menu xml end**
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
**For popup menu**

    public void showPopupMenu(View view){
        PopupMenu popupMenu = new PopupMenu (this, view);
        MenuInflater inflater =popupMenu.getMenuInflater();
        inflater.inflate(R.menu.popup_menu, popupMenu.getMenu());
        popupMenu.setOnMenuItemClickListener(new PopupMenu.OnMenuItemClickListener() {
            @Override
            public boolean onMenuItemClick(MenuItem item) {
                return onPopupMenuClick(item);
            }
        });
        popupMenu.show();
    }
    private boolean onPopupMenuClick(MenuItem item){
        int items = item.getItemId();
        if(items == R.id.ibold)
        {
            Toast.makeText(getBaseContext(),"bold clicked",Toast.LENGTH_SHORT).show();
        }
        if(items == R.id.iitalic)
        {
            Toast.makeText(getBaseContext(),"Italic clicked",Toast.LENGTH_SHORT).show();
        }
        if(items == R.id.iunderline)
        {
            Toast.makeText(getBaseContext(),"Underline clicked",Toast.LENGTH_SHORT).show();
        }
        return true;
    }
}
**For popup menu end**
 <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:onClick="showPopupMenu"
        android:text="Click for popup menu
"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/context_textview" />
Create new file:


<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <item
        android:id="@+id/ibold"
        android:title="Bold"/>
    <item
        android:id="@+id/iitalic"
        android:title="Italic"/>
    <item
        android:id="@+id/iunderline"
        android:title="underline"/>
</menu>
