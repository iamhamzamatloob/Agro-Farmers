package example.com.agrofarmers;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.Toast;

public class LoginActivity extends AppCompatActivity {

    private long backPressedTime;
    private Toast backToast;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_login);
    }

    @Override
    public void onBackPressed() {
        backPressedTime = System.currentTimeMillis();
        if (backPressedTime + 3000 > System.currentTimeMillis()) {
            super.onBackPressed();
            finish();
        }
        else
        {
            Toast.makeText(LoginActivity.this,"Press Back Again To Exit!",Toast.LENGTH_SHORT).show();
        }
    }
}
