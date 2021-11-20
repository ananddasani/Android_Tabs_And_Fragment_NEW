# Android_Tabs_And_Fragment_NEW
Controlling Tabs and Fragment Using New Class FragmentStateAdapter

# Code

#### FragmentAdapter.java
```
 public class FragmentAdapter extends FragmentStateAdapter {

    private String[] titles = {"HOME", "MOVIE", "SONG"};

    public FragmentAdapter(@NonNull FragmentActivity fragmentActivity) {
        super(fragmentActivity);
    }

    @NonNull
    @Override
    public Fragment createFragment(int position) {

        switch (position){
            case 0 : return new FragmentHome();
            case 1 : return new FragmentMovie();
            case 2 : return new FragmentSong();
        }
        return new FragmentHome();
    }

    @Override
    public int getItemCount() {
        return titles.length;
    }
}
```

#### MainActivity.java
```
private String[] titles = {"HOME", "MOVIE", "SONG"};

FragmentAdapter fragmentAdapter;
TabLayout tabLayout;
ViewPager2 viewPager2;

viewPager2 = findViewById(R.id.viewPager2);
tabLayout = findViewById(R.id.tabLayout);

fragmentAdapter = new FragmentAdapter(this);

viewPager2.setAdapter(fragmentAdapter);

new TabLayoutMediator(tabLayout, viewPager2, ((tab, position) -> tab.setText(titles[position]))).attach();
```

# App Highlight

<img src="app_images/Tabs New Code.png" width="1000" /><br>

<img src="app_images/Tabs New App1.png" width="300" /><br>

<img src="app_images/Tabs New App2.png" width="300" /><br>

<img src="app_images/Tabs New App3.png" width="300" /><br>
