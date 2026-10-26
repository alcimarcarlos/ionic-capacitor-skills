# ionic-systematic-debugging Reference

## Diagnostic Commands

```bash
# Run targeted Angular spec test
npx ng test --include src/app/pages/order-detail/order-detail.component.spec.ts --watch=false

# Check Android Studio / Device logs via ADB
adb logcat -s "Capacitor:*" "Chromium:*"

# Check iOS Simulator logs
xcrun simctl spawn booted log stream --predicate 'processImagePath contains "Capacitor"'
```

## Minimal Failing Test Template (Jasmine/Karma)

```ts
import { TestBed } from '@angular/core/testing';
import { CameraService } from './camera.service';
import { Capacitor } from '@capacitor/core';

describe('CameraService Bug Reproducer', () => {
  let service: CameraService;

  beforeEach(() => {
    TestBed.configureTestingModule({});
    service = TestBed.inject(CameraService);
  });

  it('gracefully handles photo capture when running on web browser', async () => {
    spyOn(Capacitor, 'isNativePlatform').and.returnValue(false);

    // Must not throw unhandled exception
    const result = await service.takePhoto();
    expect(result.fallbackUsed).toBeTrue();
  });
});
```
