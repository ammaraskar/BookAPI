Example Plugin for BookAPI
==========

```java
    public class Example extends JavaPlugin implements Listener{
        public void onEnable(){
            this.getServer().getPluginManager().registerEvents(this, this);		
        }
        @EventHandler
        public void onPlayerJoin(PlayerJoinEvent event){
            if(!event.getPlayer().hasPlayedBefore()){
                CraftItemStack book = new CraftItemStack(Material.WRITTEN_BOOK);
                Book b = new CraftBookBuilder().getBook(book);
                b.setTitle(ChatColor.GRAY+"GenericTitle");
                b.setAuthor(ChatColor.DARK_RED+"Administration");
                List<String> pages = new ArrayList<String>();
                pages.add(ChatColor.BLUE+"We made a Book");
                b.setPages(pages);
                event.getPlayer().setItemInHand(book);
            }
        }
    }
```