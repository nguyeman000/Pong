pongSettings.title = 'Pong';

game.players.b.speed = 200;

if (game.players.a.score == 10) {
  game.win('Player 2 wins!');
}

if (game.players.b.score == 10) {
  game.win('Player 1 wins!');
}

if (gameEvents.key.W) {
  game.players.a.move( -1 );
}

gameEvents.hit;

pongSettings.ball.size = 15;
pongSettings.ball.color = '#99ffff';
pongSettings.ball.velocity[0] = 15;
pongSettings.ball.velocity[1] = 15;

if (gameEvents.key.S) {
  game.players.a.move( 1 );
}

pongSettings.backgroundColor = '#000000';
pongSettings.linesColor = '#99ffff';

if (false) {
  if (game.balls[0].velocity.x * (Math.abs(game.balls[0].velocity.x) + 2) > 0) {
      var x  = (Math.abs(game.balls[0].velocity.x) + 2);
  } else {
      var x  = -(Math.abs(game.balls[0].velocity.x) + 2);
  }
  if (game.balls[0].velocity.y * (Math.abs(game.balls[0].velocity.x) + 2) > 0) {
      var y = (Math.abs(game.balls[0].velocity.x) + 2);
  } else {
      var y = -(Math.abs(game.balls[0].velocity.x) + 2);
  }
  window.pongSettings.ball.velocity = [x,y];
  game.setBallVelocity([ x, y ]);
}
