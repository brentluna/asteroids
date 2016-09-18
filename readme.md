# Asteroids

[Live Link](https://brentluna.github.io/asteroids/)

## Description

Browser version of the classic arcade game asteroids.

## Technologies

- JavaScript
- HTML5 Canvas
- keymaster

The game utilized Canvas to create the rendered objects (bullets, ship, asteroids). I utilized JavaScript for all the game logic, such as movement, shooting, determining if an asteroid was shot or the ship hit by an asteroid. I implemented keyboard event listeners with the Keymaster library, for user interaction with the ship.

```javascript
MovingObject.prototype.isCollidedWith = function(otherObject) {
  let dist = Math.sqrt(
    Math.pow((this.pos[0]-otherObject.pos[0]),2) + Math.pow(
      (this.pos[1]-otherObject.pos[1]),2));
  let radii = this.radius + otherObject.radius;
  return dist < radii;
};

GameView.prototype.bindKeyHandlers = function() {
  key('right', () => {
    this.game.ship.power([1, 0]);
  });
  key('left', () => {
    this.game.ship.power([-1, 0]);
  });
  key('down', () => {
    this.game.ship.power([0, 1]);
  });
  key('up', () => {
    this.game.ship.power([0, -1]);
  });
  key('space', () => {
    this.game.ship.fireBullet();
  });
};
```

## Todos

- Update styling with asteroid and ship sprites, instead of the spherical canvas objects it's currently using
- Add sound effects
